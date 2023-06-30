### getHardwareSystemInfo
|方法名|getHardwareSystemInfo|
| :--------  | :-----  |
|描述|* 获取无线电硬件信息|
|返回值|void|
|请求参数|listener（listener）
### setDataTransmissionRateListener
|方法名|setDataTransmissionRateListener|
| :--------  | :-----  |
|描述|* 获取无线电系统信道传输能力|
|返回值|void|
|请求参数|listener（listener）
### setAntennaSignalQualityListener
|方法名|setAntennaSignalQualityListener|
| :--------  | :-----  |
|描述|* 获取无线电天线物理层通讯质量|
|返回值|void|
|请求参数|listener（listener）
### setWirelessSignalQualityListener
|方法名|setWirelessSignalQualityListener|
| :--------  | :-----  |
|描述|* 获取无线电上下行信号信号质量|
|返回值|void|
|请求参数|listener（listener）
### getChannelInterfaceStatus
|方法名|getChannelInterfaceStatus|
| :--------  | :-----  |
|描述|* 设置无线电频点扫描监听|
|返回值|void|
|请求参数|listener（listener）
### getFrequencyHopping
|方法名|getFrequencyHopping|
| :--------  | :-----  |
|描述|* 获取频点配置|
|返回值|void|
|请求参数|listener（listener）
### setFrequencyHopping
|方法名|setFrequencyHopping|
| :--------  | :-----  |
|描述|* 设置无线电跳频设置|
|返回值|void|
|请求参数|frequencyRange（频点（当isAuto = false时生效））
|请求参数|isAuto（是否自动跳频）
|请求参数|callback（callback）
### getSignalBandwidth
|方法名|getSignalBandwidth|
| :--------  | :-----  |
|描述|* 获取上下行信号带宽配置|
|返回值|void|
|请求参数|listener（listener）
### setSignalBandwidth
|方法名|setSignalBandwidth|
| :--------  | :-----  |
|描述|* 设置下行信号带宽配置|
|返回值|void|
|请求参数|callback（callback）
|请求参数|bandwidthInfo（上下行配置）
### startPairing
|方法名|startPairing|
| :--------  | :-----  |
|描述|* 启动对频|
|返回值|void|

##INFO
### AntennaSignalInfo
 * 无线电模块天线物理层数据反馈

|名称|描述|
| :--------  | :----:  |
|masterNode|主节点（地面端）|
|slaveNode|从节点（天空端）|
|mainAntenna|主天线|
|subAntenna|辅天线|
|-1|自动增益|
|WirelessLevelState.UNKNOWN|无线电信号等级|
|-1|接收信号功率|
|-1|接收信号强度|
|-1|信噪比|
### WirelessBandwidthInfo
 * 无线电带宽信息

|名称|描述|
| :--------  | :----:  |
|uplinkSignalBandwidth|上行带宽设定|
|downloadSignalBandwidth|下行带宽设定|
### WirelessChannelInterfaceInfo
 * 无线电频点信息

|名称|描述|
| :--------  | :----:  |
|freqCount|频点列表数量|
|freqPrefer|当前选用频点|
|freqList|频点列表|
|interferenceList|干扰值列表|
### WirelessDataTransmissionInfo
 * 无线电信号传输状态

|名称|描述|
| :--------  | :----:  |
|upLinkPhysicsCapacity|上行带宽模式|
|downLinkPhysicsCapacity|下行带宽模式|
|wirelessFrequencyPoint|当前选用频点|
|downLinkDataCapacity|下行数据带宽理论值|
|downLinkDataSpeed|当前下行数据带宽|
|upLinkDataCapacity|上行数据带宽理论值|
|upLinkDataSpeed|当前上行数据带宽|
### WirelessFrequencyInfo
 * 无线电频点设定

|名称|描述|
| :--------  | :----:  |
|isAutoHopping|是否自动跳频|
|frequencyPoint|手动频点-当hopping=true时无效|
### WirelessHardwareInfo
 * 无线电硬件信息

|名称|描述|
| :--------  | :----:  |
|mainNode|主节点（地面端）|
|subNode|从节点（天空端）|
|id|设备ID|
|version|设备版本|
|mac|设备MAC地址|
|uptime|设备上电时间|
### WirelessSignalInfo
 * 无线电信号等级

|名称|描述|
| :--------  | :----:  |

##ENUM
### BandWidthState
 * 无线电带宽模式

|名称|值|描述|
| :--------  | :-----  | :----:  |
|BW_1Dot4MHz|0|1.4Mhz|
|BW_10MHz|3|10Mhz|
|BW_20MHz|5|20Mhz|
|BW_UNKNOWN|-1|unknown|
### WirelessLevelState
 * 无线电信号等级

|名称|值|描述|
| :--------  | :-----  | :----:  |
|GREAT|1|极佳|
|GOOD|2|一般|
|BAD|3|较差|
|UNKNOWN|-1|未知|
