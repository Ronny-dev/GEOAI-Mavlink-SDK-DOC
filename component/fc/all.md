##INTERFACE
###setFlyControllerStateListener
|方法名|setFlyControllerStateListener|
| :--------  | :-----  |
|描述||
|返回值|void|
|请求参数|listener（listener）
|设置飞行器状态监听{link|com.geoai.mavlink.geoainet.flycontroller.info.FlyControllerStateInfo}|
###setDiagnosticsStateListener
|方法名|setDiagnosticsStateListener|
| :--------  | :-----  |
|描述|* 设置飞行器HMS系统状态监听回调（健康管理系统）|
|返回值|void|
|请求参数|listener（listener）
###startAircraftTakeoff
|方法名|startAircraftTakeoff|
| :--------  | :-----  |
|描述|* 发送无人机起飞指令；无人机会起飞到1.2m后悬停|
|返回值|void|
|请求参数|callback（callback）
###startAircraftTakeoff
|方法名|startAircraftTakeoff|
| :--------  | :-----  |
|描述|* 发送无人机起飞指令|
|返回值|void|
|请求参数|altitude（起飞悬停高度）
|请求参数|callback（callback）
###startAircraftLand
|方法名|startAircraftLand|
| :--------  | :-----  |
|描述|* 发送无人机降落指令|
|返回值|void|
|请求参数|callback（callback）
###stopAircraftLand
|方法名|stopAircraftLand|
| :--------  | :-----  |
|描述|* 发送无人机取消降落指令|
|返回值|void|
|请求参数|callback（callback）
###startAircraftGoHome
|方法名|startAircraftGoHome|
| :--------  | :-----  |
|描述|* 发送无人机返航指令；无人机会先升高到返航高度后返航|
|返回值|void|
|请求参数|callback（callback）
###startAircraftReturn
|方法名|startAircraftReturn|
| :--------  | :-----  |
|描述|* 发送无人机返航指令；具体返航动作详看说明书|
|返回值|void|
|请求参数|callback（callback）
|请求参数|type（返航模式）
###startAircraftReturnAssignRally
|方法名|startAircraftReturnAssignRally|
| :--------  | :-----  |
|描述|* 发送无人机返航指令；前往指定的备降点|
|返回值|void|
|请求参数|index（index）
|请求参数|callback（callback）
###stopAircraftGoHome
|方法名|stopAircraftGoHome|
| :--------  | :-----  |
|描述|* 发送无人机取消返航指令|
|返回值|void|
|请求参数|callback（callback）
###setGoHomeAltitude
|方法名|setGoHomeAltitude|
| :--------  | :-----  |
|描述|* 设置无人机返航高度|
|返回值|void|
|请求参数|altitude（返航高度）
|请求参数|callback（callback）
###getGoHomeAltitude
|方法名|getGoHomeAltitude|
| :--------  | :-----  |
|描述|* 获取无人机返航高度|
|返回值|void|
|请求参数|callback（callback）
###getGoHomeLocation
|方法名|getGoHomeLocation|
| :--------  | :-----  |
|描述|* 获取无人机当前返航点坐标|
|返回值|void|
|请求参数|callback（callback）
###stopAllAction
|方法名|stopAllAction|
| :--------  | :-----  |
|描述|* 终止飞行器动作指令并悬停|
|返回值|void|
|请求参数|callback（callback）
###startForceLanding
|方法名|startForceLanding|
| :--------  | :-----  |
|描述|* 发送无人机强制降落（不会进入视觉降落程序）|
|返回值|void|
|请求参数|callback（callback）
###setDroneArm
|方法名|setDroneArm|
| :--------  | :-----  |
|描述|* 飞机上锁|
|返回值|void|
|请求参数|callback（callback）
###setDroneDisarm
|方法名|setDroneDisarm|
| :--------  | :-----  |
|描述|* 飞机解锁|
|返回值|void|
|请求参数|callback（callback）
###setJoyStickEnable
|方法名|setJoyStickEnable|
| :--------  | :-----  |
|描述|* 飞行器启动虚拟摇杆|
|返回值|void|
|请求参数|callback（callback）
###sendJoyStickControl
|方法名|sendJoyStickControl|
| :--------  | :-----  |
|描述|* 发送虚拟摇杆指令（美国手）|
|返回值|void|
|请求参数|r（yaw）
|请求参数|x（pitch）
|请求参数|y（roll）
|请求参数|callback（callback）
|请求参数|z（throttle）
###getAlternateLandingPoints
|方法名|getAlternateLandingPoints|
| :--------  | :-----  |
|描述|* 获取备降点|
|返回值|void|
|请求参数|callback（callback）
###setAlternateLandingPoints
|方法名|setAlternateLandingPoints|
| :--------  | :-----  |
|描述|* 设置备降点|
|返回值|void|
|请求参数|callback（callback）
|请求参数|points（备降点列表）
##INFO
###AircraftDiagnosticsStateInfo
 * hms健康管理系统状态回调

|名称|描述|
| :--------  | :----:  |
|alertCode|告警错误码|
|alertIndex|告警序列|
|alertLevel|告警等级|
|timestamp|告警时间|
###FlyControllerStateInfo
 * 飞控系统状态回调

|名称|描述|
| :--------  | :----:  |
|aircraftLatitude|飞行器融合纬度|
|aircraftLongitude|飞行器融合经度|
|aircraftAltitude|飞行器融合高度|
|aircraftPitch|飞行器pitch姿态角|
|aircraftRoll|飞行器roll姿态角|
|aircraftYaw|飞行器yaw姿态角|
|aircraftVelocityX|飞行器机身坐标系x轴速度|
|aircraftVelocityY|飞行器机身坐标系y轴速度|
|aircraftVelocityZ|飞行器机身坐标系z轴速度|
|aircraftGpsSatelliteNumber|飞行器GPS卫星数|
|aircraftHomeLatitude|飞行器返航点纬度|
|aircraftHomeLongitude|飞行器返航点经度|
|flyMode|当前飞控模式|
|isMotorsOn|当前电机是否启动|
|isFlying|当前飞机是否在空中|
|flyTime|飞行器飞行时间|
|posType|当前飞行器定位模式|
|aircraftReturnLatitude|飞行器返回点纬度|
|aircraftReturnLongitude|飞行器返回点经度|
|aircraftReturnDestinationType|飞行器返航点类型|
|aircraftReturnMode|飞行器返航路径类型|
|aircraftReturnState|飞行器返航动作|
##ENUM
###AircraftReturnMode
 * 飞机返航模式枚举类型，用于描述飞机的返航模式。

|名称|值|描述|
| :--------  | :-----  | :----:  |
|RTL_TYPE_DEFAULT|0|默认方式返航。（返航方式取决于参数RTL_TYPE）|
|RTL_TYPE_MISSION_LANDING|1|直线返回（最近的）降落点、备降点。|
|RTL_TYPE_MISSION_LANDING_REVERSED|2|如果存在降落点，则沿路径返回降落点，否则沿原路径返回home点。|
|RTL_TYPE_CLOSEST|3|直线返回（最近的）home点、降落点、备降点。|
|RTL_TYPE_CLOSEST_HOME_LAND|4|直线返回（最近的）home点、降落点。|
|RTL_TYPE_HOME|5|直线返回home点。|
|RTL_TYPE_LAND|6|直线返回降落点（如果不存在降落点，则返回home点）。|
|RTL_TYPE_CLOSEST_RALLY|7|直线返回最近的备降点。（如果不存在备降点，则返回最近的home点或降落点）|
|RTL_TYPE_ASSIGN_RALLY|8|直线返回指定的备降点。（如果不存在备降点，则返回最近的home点或降落点）|
|RTL_TYPE_BY_PASS_CLOSEST_HOME_LAND|9|沿路径返回（最近的）home点、降落点。|
|RTL_TYPE_BY_PASS_CLOSEST_HOME|10|沿路径返回home点。|
|RTL_TYPE_BY_PASS_LAND|11|沿路径返回降落点。（如果不存在降落点，则返回home点）|
|RTL_TYPE_HOME_OR_RALLY|12|直线返回（最近的）home点、备降点。|
###AircraftReturnState
 * 飞机返航状态枚举类型，用于描述飞机当前的返航状态。

|名称|值|描述|
| :--------  | :-----  | :----:  |
|RTL_STATE_NONE|0|未返航|
|RTL_STATE_CLIMB|1|爬升|
|RTL_STATE_RETURN|2|直线飞往返航目标点|
|RTL_STATE_DESCEND|3|固定翼模式下降|
|RTL_STATE_LOITER|4|悬停等待|
|RTL_STATE_TRANSITION_TO_MC|5|切换成旋翼|
|RTL_MOVE_TO_LAND_HOVER_VTOL|6|垂起飞机旋翼模式飞往目标点|
|RTL_STATE_LAND|7|降落|
|RTL_STATE_LANDED|8|降落完成|
|RTL_STATE_HEAD_TO_CENTER|9|调整返航朝向|
|RTL_STATE_BY_PASS|10|沿路径飞往目标返航点|
