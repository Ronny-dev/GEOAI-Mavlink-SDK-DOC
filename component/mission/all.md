### uploadMission
|方法名|uploadMission|
| :--------  | :-----  |
|描述|* 上传任务|
|返回值|void|
|请求参数|listener（listener）
|请求参数|missionItemBuilder（任务构建器{link MissionItemBuilder}）
### startMission
|方法名|startMission|
| :--------  | :-----  |
|描述|* 启动任务|
|返回值|void|
|请求参数|callback（callback）
### pauseMission
|方法名|pauseMission|
| :--------  | :-----  |
|描述|* 暂停任务|
|返回值|void|
|请求参数|callback（callback）
### continueMission
|方法名|continueMission|
| :--------  | :-----  |
|描述|* 继续任务|
|返回值|void|
|请求参数|callback（callback）
### stopMission
|方法名|stopMission|
| :--------  | :-----  |
|描述|* 停止任务|
|返回值|void|
|请求参数|callback（callback）
### stopMissionUpload
|方法名|stopMissionUpload|
| :--------  | :-----  |
|描述|* 停止上传任务|
|返回值|void|
|请求参数|callback（callback）
### setMissionStateListener
|方法名|setMissionStateListener|
| :--------  | :-----  |
|描述|* 设置任务航线执行过程监听|
|返回值|void|
|请求参数|mMissionStateListener（listener）
### sendPositionCommand
|方法名|sendPositionCommand|
| :--------  | :-----  |
|描述|* 直接通知飞行器前往指定坐标，不会触发所有任务逻辑|
|返回值|void|
|请求参数|altitude（高度）
|请求参数|latitude（纬度）
|请求参数|callback（callback）
|请求参数|speed（速度）
|请求参数|longitude（经度）
### sendOrbitCommand
|方法名|sendOrbitCommand|
| :--------  | :-----  |
|描述|* 使飞行器在指定位置盘旋，不会触发所有任务逻辑|
|返回值|void|
|请求参数|altitude（高度）
|请求参数|yawBehaviour（航向模式）
|请求参数|latitude（纬度）
|请求参数|callback（callback）
|请求参数|radius（半径）
|请求参数|speed（速度）
|请求参数|longitude（经度）
##INFO
### MissionStateInfo
 * 用于描述任务整体状态

|名称|描述|
| :--------  | :----:  |
|MissionUploadState.UNKNOWN|任务上传状态|
|MissionState.UNKNOWN|航线执行状态|
|totalWaypoint|航点总数|
|currentReachWaypointIndex|当前到达航点序列|
|currentActionIndex|当前执行的航点动作序列|
##ENUM
### null
null
|名称|值|描述|
| :--------  | :-----  | :----:  |
### MissionState
 * 用于描述航线执行状态

|名称|值|描述|
| :--------  | :-----  | :----:  |
|READY_TO_UPLOAD|0|等待上传|
|UPLOADING|1|上传中|
|READY_TO_EXECUTE|2|等待执行|
|EXECUTING|3|执行中|
|PAUSING|4|暂停中|
|FINISHED|5|已完成|
|UNKNOWN|55|未知|
### MissionUploadState
 * 用于判断当前任务上传进度

|名称|值|描述|
| :--------  | :-----  | :----:  |
|READY_TO_UPLOAD,|-1|等待上传|
|INITIALLING,|-1|正在建立连接|
|INITIALLED,|-1|已建立连接，准备传输|
|UPLOADING,|-1|上传中|
|UPLOADED,|-1|上传完成|
|READY_TO_EXECUTE,|-1|等待执行|
|FAILED,|-1|上传失败|
|UNKNOWN|-1|未知|
### null
null
|名称|值|描述|
| :--------  | :-----  | :----:  |
|ORBIT_YAW_BEHAVIOUR_HOLD_FRONT_TO_CIRCLE_CENTER|0|指向兴趣点|
|ORBIT_YAW_BEHAVIOUR_HOLD_INITIAL_HEADING|1|保持初始航向|
|ORBIT_YAW_BEHAVIOUR_UNCONTROLLED|2|航向不进行控制|
|ORBIT_YAW_BEHAVIOUR_HOLD_FRONT_TANGENT_TO_CIRCLE|3|航向遵循飞行路径（相切）|
|ORBIT_YAW_BEHAVIOUR_RC_CONTROLLED|4|由RC输入控制|
|UNKNOWN|0|默认0.|
### null
null
|名称|值|描述|
| :--------  | :-----  | :----:  |
