## Documentation

#### `void sendRTCM(byte[] bytes)`

从地面站发送RTCM差分数据到飞控，请自行甄别差分数据的真实性

 * **Parameters:** `bytes` — 0xD3 0x00 ....

### `void setRtkStateListener(IRtkStateListener listener)`

设置RTK组件的回调信息

 * **Parameters:** `listener` — listener

### `void setRtkEnable(boolean isEnable)`

设置飞行器是否打开RTK功能

 * **Parameters:** `isEnable` — isEnable

### `boolean getRtkEnable()`

获取飞行器当前是否处于RTK模式

 * **Returns:** isEnable

### `boolean setNtripAuthInfo(NtripAuthInfo info)`

设置连接RTK的Ntrip服务账密信息

 * **Parameters:** `info` — 用户Ntrip连接信息
 * **Returns:** 是否保存成功

### `NtripAuthInfo getNtripAuthInfo()`

获取保存在SDK中的Ntrip服务账密信息

 * **Returns:** 用户Ntrip连接信息

### `void connectToNtripRTK(INtripServerConnectListener listener)`

连接RTK服务 请确保在调用此API前已经成功设定Ntrip账密信息{@link IBaseRtkManager#setNtripAuthInfo(NtripAuthInfo)} 回调信息也可以通过{@link IBaseRtkManager#setRtkStateListener(IRtkStateListener)}接口获取

 * **Parameters:** `listener` — 

### `void disconnectNtripServer()`

断开RTK服务 若用户已经连接了RTK，则可能短时间内仍保持RTK状态

### `boolean isNtripServerConnected()`

当前是否与设定的NtripServer进行RTCM数据传输

 * **Returns:** isConnected