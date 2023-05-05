### getAirLinkState
|方法名|getAirLinkState|
| :--------  | :-----  |
|描述|* 获取地面电台状态信息|
|返回值|MeshHelper2.MeshStatus（{link）|
|云冠|不支持|
### void sendATCommand
|方法名|void sendATCommand|
| :--------  | :-----  |
|描述|* 发送AT指令到连接中的无线电模块|
|返回值|void|
|请求参数|at（AT指令）
|请求参数|callback（callback）
|云冠|不支持|
### setAirLinkStateListener
|方法名|setAirLinkStateListener|
| :--------  | :-----  |
|描述||
|返回值|void|
|请求参数|listener（listener）
|云冠|不支持|
|设置地面电台模块监听的回调{link|com.geoai.mavlink.util.MeshHelper2.MeshStatus}|
### isAirLinkConnected
|方法名|isAirLinkConnected|
| :--------  | :-----  |
|描述|* 获取当前地面电台是否正常连接|
|返回值|void|
|请求参数|callback（callback）
|云冠|不支持|
### getHardwareAirLinkVersion
|方法名|getHardwareAirLinkVersion|
| :--------  | :-----  |
|描述|* 获取地面电台硬件版本号|
|返回值|void|
|请求参数|callback（callback）
|云冠|不支持|
### getAirLinkSerialNumber
|方法名|getAirLinkSerialNumber|
| :--------  | :-----  |
|描述|* 获取地面电台序列号|
|返回值|void|
|请求参数|callback（callback）
|云冠|不支持|
### airLinkRestart
|方法名|airLinkRestart|
| :--------  | :-----  |
|描述|* 地面电台重启|
|返回值|void|
|请求参数|callback（callback）
|云冠|不支持|
### setSecurityCode
|方法名|setSecurityCode|
| :--------  | :-----  |
|描述|* 设置指定的秘钥|
|返回值|void|
|请求参数|code（security code）
|请求参数|callback（callback）
|云冠|不支持|
### getSecurityCode
|方法名|getSecurityCode|
| :--------  | :-----  |
|描述|* 获取当前无线电密钥|
|返回值|void|
|请求参数|callback（callback）
|云冠|不支持|
### setPairListener
|方法名|setPairListener|
| :--------  | :-----  |
|描述|* 单独设置对频的监听器|
|返回值|void|
|请求参数|listener（listener）
|云冠|不支持|
### enterPairMode
|方法名|enterPairMode|
| :--------  | :-----  |
|描述|* 进入对频模式|
|返回值|void|
|请求参数|listener（callback）
|云冠|不支持|
### exitPairMode
|方法名|exitPairMode|
| :--------  | :-----  |
|描述|* 退出对频模式|
|返回值|void|
|请求参数|callback（callback）
|云冠|不支持|
##INFO
##ENUM
### PairStatusInfo
* 飞行器与地面站对频状态枚举，用于描述当前对频处于什么模式中

|名称|值|描述|
| :--------  | :-----  | :----:  |
|SAVE_SECURITY_CODE|1|地面站保存无线电秘钥|
|ENTER_PUBLIC_SECURITY_CODE|2|进入公共秘钥频段|
|WAIT_ONLINE|3|等待公共秘钥中的远端无人机上线连接|
|SECURITY_CODE_TRAN|4|传输私有秘钥|
|WAIT_ONLINE2|5|等待私有秘钥中的远端无人机上线连接|
|EXIT_PAIRING|6|退出对频模式|
|UNKNOWN|0|未知状态|
