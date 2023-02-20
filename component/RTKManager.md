### Documentation

#### `void sendRTCM(byte[] bytes)`

用于单独向飞行控制器发送RTCM数据。 它要求开发者自己验证差分数据的真实性。

* **Parameters:** `bytes` — RTCM数据

#### `void setRtkStateListener(IRtkStateListener listener)`

这是一个异步接口，用于获取RTK组件状态。 用户需要提供一个回调函数来处理RTK组件返回的消息。

* **Parameters:** `listener` — 提供飞行器位置和网络rtk相关状态信息的RtkEntryInfo对象
* **See also:** RtkEntryInfo {@link RtkEntryInfo}

#### `void setRtkEnable(boolean isEnable)`

启用或禁用RTK功能。 请注意，如果飞机在空中获得了固定解，调用此方法禁用RTK后将保持RTK精度一段时间。 但是飞行的过程可能导致飞机位置跳跃。

* **Parameters:** `isEnable` — 启动或关闭RTK功能

#### `boolean getRtkEnable()`

获取飞行器当前是否处于RTK模式

* **Returns:** 当前是否处于RTK模式

#### `boolean setNtripAuthInfo(NtripAuthInfo info)`

设置连接RTK的Ntrip服务账密信息

* **Parameters:** `info` — 用户Ntrip连接信息
* **Returns:** 是否保存成功

#### `NtripAuthInfo getNtripAuthInfo()`

获取保存在SDK中的Ntrip服务账密信息

* **Returns:** 用户Ntrip连接信息

#### `void connectToNtripRTK(INtripServerConnectListener listener)`

连接RTK服务 请确保在调用此API前已经成功设定Ntrip账密信息{@link IBaseRtkManager#setNtripAuthInfo(NtripAuthInfo)} 回调信息也可以通过{@link IBaseRtkManager#setRtkStateListener(IRtkStateListener)}接口获取

* **Parameters:** `listener` —

#### `void disconnectNtripServer()`

断开RTK服务 若用户已经连接了RTK，则可能短时间内仍保持RTK状态

#### `boolean isNtripServerConnected()`

当前是否与设定的NtripServer进行RTCM数据传输

* **Returns:** isConnected