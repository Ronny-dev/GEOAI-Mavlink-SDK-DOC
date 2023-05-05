### setLteStateListener
|方法名|setLteStateListener|
| :--------  | :-----  |
|描述|* 设置机载电脑LTE模块状态|
|返回值|void|
|请求参数|listener（listener）
|云冠|支持|
### setYoloV5DetectionEnable
|方法名|setYoloV5DetectionEnable|
| :--------  | :-----  |
|描述|* 设置云冠Yolo识别框架是否启动|
|返回值|void|
|请求参数|callback（callback）
|请求参数|isYoloEnable（是否开启视觉识别）
### getYoloV5DetectionEnable
|方法名|getYoloV5DetectionEnable|
| :--------  | :-----  |
|描述|* 获取云冠Yolo识别框架是否启动|
|返回值|void|
|请求参数|callback（callback）
### setCrestMqttIpAddress
|方法名|setCrestMqttIpAddress|
| :--------  | :-----  |
|描述|* 设置MQTT连接地址|
|返回值|void|
|请求参数|ipAddress（MQTT地址[...]）
|请求参数|callback（callback）
### getCrestMqttIpAddress
|方法名|getCrestMqttIpAddress|
| :--------  | :-----  |
|描述|* 获取MQTT连接地址|
|返回值|void|
|请求参数|callback（callback）
### setCrestMqttConnectionPort
|方法名|setCrestMqttConnectionPort|
| :--------  | :-----  |
|描述|* 设置MQTT连接端口|
|返回值|void|
|请求参数|port（port）
|请求参数|callback（callback）
### getCrestMqttConnectionPort
|方法名|getCrestMqttConnectionPort|
| :--------  | :-----  |
|描述|* 获取MQTT连接端口|
|返回值|void|
|请求参数|callback（callback）
### setCrestMqttConnectionUserName
|方法名|setCrestMqttConnectionUserName|
| :--------  | :-----  |
|描述|* 设置MQTT连接用户名|
|返回值|void|
|请求参数|callback（callback）
|请求参数|userName（username）
### getCrestMqttConnectionUserName
|方法名|getCrestMqttConnectionUserName|
| :--------  | :-----  |
|描述|* 获取MQTT连接用户名|
|返回值|void|
|请求参数|callback（callback）
### setCrestMqttConnectionPassword
|方法名|setCrestMqttConnectionPassword|
| :--------  | :-----  |
|描述|* 设置MQTT连接密码|
|返回值|void|
|请求参数|password（password）
|请求参数|callback（callback）
### getCrestMqttConnectionPassword
|方法名|getCrestMqttConnectionPassword|
| :--------  | :-----  |
|描述|* 获取MQTT连接密码|
|返回值|void|
|请求参数|callback（callback）
### setCrestLteEnable
|方法名|setCrestLteEnable|
| :--------  | :-----  |
|描述|* 设置机载电脑LTE模块开关|
|返回值|void|
|请求参数|callback（callback）
|请求参数|isEnable（LTE是否打开）
### getCrestLteEnable
|方法名|getCrestLteEnable|
| :--------  | :-----  |
|描述|* 获取机载电脑LTE模块开关|
|返回值|void|
|请求参数|callback（callback）
### setCrestPingServer
|方法名|setCrestPingServer|
| :--------  | :-----  |
|描述|* 设置机载电脑网络检测服务器|
|返回值|void|
|请求参数|ipAddress（用于ping检测的服务器地址）
|请求参数|callback（callback）
### getCrestPingServer
|方法名|getCrestPingServer|
| :--------  | :-----  |
|描述|* 获取机载电脑网络检测服务器|
|返回值|void|
|请求参数|callback（callback）
### setRtmpPushEnable
|方法名|setRtmpPushEnable|
| :--------  | :-----  |
|描述|* 设置机载电脑RTMP推流开关|
|返回值|void|
|请求参数|callback（callback）
|请求参数|isEnable（是否打开推流）
### getRtmpPushEnable
|方法名|getRtmpPushEnable|
| :--------  | :-----  |
|描述|* 获取机载电脑RTMP推流开关|
|返回值|void|
|请求参数|callback（callback）
### setRtmpPushUrl
|方法名|setRtmpPushUrl|
| :--------  | :-----  |
|描述|* 设置RTMP推流地址|
|返回值|void|
|请求参数|callback（callback）
|请求参数|url（推流地址 [设置成功请重新使能RTMP开关]）
### getRtmpPushUrl
|方法名|getRtmpPushUrl|
| :--------  | :-----  |
|描述|* 获取RTMP推流地址|
|返回值|void|
|请求参数|callback（callback）
##INFO
### Rm500HardwareStateInfo
* 机载电脑4G/5G硬件状态回调

|名称|描述|
| :--------  | :----:  |
|lteModuleTemperature|lte模块温度|
|lteReferenceSignalReceivingPower|lte模块信号接收功率|
|lteSignalInterferenceNoiseRatio|lte模块信噪比|
##ENUM
