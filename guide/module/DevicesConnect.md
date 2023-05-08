# 设备连接教程

### 名词解释

UDP链路：无线电链路

MQTT链路：云冠使用4G、5G传输数传信息

P2P链路：使用VPN技术透传数传信息

---

### 如何连接设备（云冠/自研飞控）

根据[配置说明](https://ronny-dev.github.io/GEOAI-Mavlink-SDK-DOC/#/guide/AndroidStudioGuide) 创建工程，并下载和注册MavSDK后进行相关激活。

- 设置设备连接监听器

```java
StarLinkClientManager.getInstance().setProductConnectionListener();
```

- 启动连接

```java
StarLinkClientManager.getInstance().openConnection();
```

当设备正常连接MavSDK后，相关ProductManager的回调会从setProductConnectionListener中进行回调，用户可以拿到ProductManager后进行相关的业务开发。

---

### 多台无人机同时连接

根据前期架构设计，当有多台无人机同时接入MavSDK后，在连接监听器中均会有回调。用户可以在ProductConnected()进行相关的监听。

- droneIndex: 无人机的SYSID
- ProductManager: 内部组件实例

```java
void onProductConnected(int droneIndex, ProductManager productManager)
```

### 多链路连接使用说明

在MavSDK中原生支持同时连接三条链路的数据，并且可支持三条数据同时接收数据并融合上传。

- UDP链路
- MQTT链路
- P2P链路

通常来讲，用户如果想要连接MQTT链路或者P2P链路，需要使用UDP链路并正常连接之后，SDK会自动与云冠做数据交互，传输必要的MQTT和P2P链路的关键信息（如MQTT信息，P2P秘钥信息）。**所以，如果希望使用4G链路或P2P链路，请务必先使用UDP链路进行首次连接。**

当客户环境不满足UDP链路连接的情况下（比如云冠2NX、云冠2Pro），设备无法使用无线电链路的情况下，可以使用SDK内部暴露的接口进行MQTT链路或者P2P链路的手动连接。

- 连接MQTT链路

```java
// 云冠jetson唯一码
StarLinkClientManager.getInstance().addMqttCrestByJetsonID(...JETSONID...);
```

- 连接P2P链路

```java
// 云冠P2P链路IP地址
StarLinkClientManager.getInstance().addP2pCrestByIpAddress(...IPADDRESS...);
```

---

### 设置多链路连接监听&多链路优先级

用户可以通过如下API获取当前使用哪个数据链路进行数据交互：

```java
ProductManager.setProductConnectionListener(IProductConnectionListener listener) {
    void onConnectionType(@Nullable ProductConnectionState state);
}
```

其中的`ProductConnectionState` 描述了下面几个信息

1. 无人机系统的SYSID
2. UDP链路的连接状态
3. MQTT链路的连接状态
4. P2P链路的连接状态

其中`AirLinkConnectionStatus` 描述的枚举包含如下几个信息

- *`DISCONNECTED` 链路未连接*
- *`CONNECTING` 链路连接中*
- *`CONNECTED` 链路已连接*
- *`TRANS` 链路使用中*
- *`ERROR` 连接错误/未知错误*

目前设计上，系统优先使用UDP链路进行连接（无线电链路）；当UDP链路掉线或者心跳接收超时后，若MQTT链路就绪，则会自动切换到MQTT链路；若MQTT链路也不在线，则会切换到P2P链路。当三条链路均无连接后，客户端会收到disconnect的回调。相关优先级如下展示

1. 无线电链路
2. MQTT链路
3. P2P链路

掉线是监听实例可以参考如下API：

```java
StarLinkClientManager.getInstance().setProductConnectionListener();
```

---

### 相关说明教程

P2P链路技术：https://github.com/Ronny-dev/Zerotier-zt

P2P链路官方说明：https://github.com/zerotier/ZeroTierOne

Zerotier官方地址：[https://docs.zerotier.com/sockets/tutorial.html](https://docs.zerotier.com/sockets/tutorial.html)

地面站心跳协议：[https://mavlink.io/en/services/heartbeat.html](https://mavlink.io/en/services/heartbeat.html)

QGC设备发现：[https://github.com/mavlink/qgroundcontrol/blob/master/src/Vehicle/MultiVehicleManager.cc](https://github.com/mavlink/qgroundcontrol/blob/master/src/Vehicle/MultiVehicleManager.cc)