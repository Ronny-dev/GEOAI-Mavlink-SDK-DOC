### sendRTCM
|方法名|sendRTCM|
| :--------  | :-----  |
|描述|* 用于单独向飞行控制器发送RTCM数据。     * 它要求开发者自己验证差分数据的真实性。|
|返回值|void|
|请求参数|bytes（RTCM数据）
### setRtkStateListener
|方法名|setRtkStateListener|
| :--------  | :-----  |
|描述|* 这是一个异步接口，用于获取RTK组件状态。     * 用户需要提供一个回调函数来处理RTK组件返回的消息。|
|返回值|void|
|请求参数|listener（提供飞行器位置和网络rtk相关状态信息的RtkEntryInfo对象）
|see|RtkEntryInfo|
### setRtkEnable
|方法名|setRtkEnable|
| :--------  | :-----  |
|描述|* 启用或禁用RTK功能。     * 请注意，如果飞机在空中获得了固定解，调用此方法禁用RTK后将保持RTK精度一段时间。     * 但是飞行的过程可能导致飞机位置跳跃。|
|返回值|void|
|请求参数|isEnable（启动或关闭RTK功能）
### getRtkEnable
|方法名|getRtkEnable|
| :--------  | :-----  |
|描述|* 获取飞行器当前是否处于RTK模式|
|返回值|boolean（当前是否处于RTK模式）|
### setNtripAuthInfo
|方法名|setNtripAuthInfo|
| :--------  | :-----  |
|描述|* 设置连接RTK的Ntrip服务账密信息|
|返回值|boolean（是否保存成功）|
|请求参数|info（用户Ntrip连接信息）
### getNtripAuthInfo
|方法名|getNtripAuthInfo|
| :--------  | :-----  |
|描述|* 获取保存在SDK中的Ntrip服务账密信息|
|返回值|NtripAuthInfo（用户Ntrip连接信息）|
### connectToNtripRTK
|方法名|connectToNtripRTK|
| :--------  | :-----  |
|描述|* 连接RTK服务|
|返回值|void|
|请求参数|listener（listener）
|请确保在调用此API前已经成功设定Ntrip账密信息{link|IBaseRtkManager#setNtripAuthInfo(NtripAuthInfo)}|
|回调信息也可以通过{link|IBaseRtkManager#setRtkStateListener(IRtkStateListener)}接口获取|
### disconnectNtripServer
|方法名|disconnectNtripServer|
| :--------  | :-----  |
|描述|* 断开RTK服务     * 若用户已经连接了RTK，则可能短时间内仍保持RTK状态|
|返回值|void|
### isNtripServerConnected
|方法名|isNtripServerConnected|
| :--------  | :-----  |
|描述|* 当前是否与设定的NtripServer进行RTCM数据传输|
|返回值|boolean（isConnected）|
##INFO
### NtripAuthInfo
* ntrip服务器身份验证

|名称|描述|
| :--------  | :----:  |
|ipAddress|Ntrip服务器ip地址|
|port|NtripServer服务端口|
|username|用户名|
|password|密码|
|mountPoint|挂载点|
### RtkEntryInfo
* RTK状态信息返回

|名称|描述|
| :--------  | :----:  |
|0.0D|飞行器融合返回的纬度|
|0.0D|飞行器融合返回的经度|
|0.0D|飞行器融合返回的高度MSL|
|baselineTimestamp|RTK组件基线时间戳|
|gpsTimeOfWeek|GPS时间|
|rtkReceiverIdentity|RTK接收机身份码|
|gpsWeekNumber|GPS周数|
|isHealth|RTK是否健康|
|rateOfGpsReceived|RTK接收消息速率|
|satelliteCount|RTK参与计算卫星数|
|accuracy|RTK估算精准度|
|ntripServiceCode|RTK网络服务返回码|
|nmeaGGA|飞行器NMEA报文-GGA|
|posType|当前RTK定位状态|
##ENUM
