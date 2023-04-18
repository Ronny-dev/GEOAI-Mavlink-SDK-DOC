### setGimbalStateListener
|方法名|setGimbalStateListener|
| :--------  | :-----  |
|描述|* 设置云台状态监听|
|返回值|void|
|请求参数|listener（listener）
|云冠|支持|
### setGimbalSpeedControl
|方法名|setGimbalSpeedControl|
| :--------  | :-----  |
|描述|* 设置云台速度控制|
|返回值|void|
|请求参数|yawRate（yaw）
|请求参数|callback（callback）
|请求参数|pitchRate（pitch）
|云冠|不支持|
### setGimbalAngleControl
|方法名|setGimbalAngleControl|
| :--------  | :-----  |
|描述|* 设置云台角度控制|
|返回值|void|
|请求参数|pitchAngle（pitch）
|请求参数|yawAngle（yaw）
|请求参数|isAbsolute（大地坐标系/机身坐标系）
|请求参数|callback（callback）
|云冠|支持|
### setGimbalPitch
|方法名|setGimbalPitch|
| :--------  | :-----  |
|描述|* 设置云台俯仰轴角度控制|
|返回值|void|
|请求参数|pitchAngle（pitch）
|请求参数|callback（callback）
|云冠|支持|
### resetGimbal
|方法名|resetGimbal|
| :--------  | :-----  |
|描述|* 重置云台（归中）|
|返回值|void|
|请求参数|callback（callback）
|云冠|支持|
### resetGimbalAndDown
|方法名|resetGimbalAndDown|
| :--------  | :-----  |
|描述|* 重置云台并垂直朝下（朝下）|
|返回值|void|
|请求参数|callback（callback）
|云冠|支持|
##INFO
### GimbalStateInfo
 * 云台状态回调

|名称|描述|
| :--------  | :----:  |
|isConnected|云台是否连接|
|deviceID|云台设备ID|
|pitchRadian|pitch弧度|
|yawRadian|yaw弧度|
|rollRadian|roll弧度|
|pitchAngle|pitch角度|
|yawAngle|yaw角度|
|rollAngle|roll角度|
|angularVelocityX|x轴角速度|
|angularVelocityY|y轴角速度|
|angularVelocityZ|z轴角速度|
##ENUM
