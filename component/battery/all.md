### setBatteryStateListener
|方法名|setBatteryStateListener|
| :--------  | :-----  |
|描述|* 设置飞行器电池状态监听|
|返回值|void|
|请求参数|batteryStateListener（电池回调）
|see|BatteryStateInfo|
### getBatteryExtraInfo
|方法名|getBatteryExtraInfo|
| :--------  | :-----  |
|描述|* 获取电池额外提供的信息|
|返回值|ExtBatteryStateInfo（电池信息）|
|see|ExtBatteryStateInfo|
|apiNote|如果接入多组电池，仅返回第一组|
### getBatteryExtraInfo
|方法名|getBatteryExtraInfo|
| :--------  | :-----  |
|描述|* 获取电池额外提供的信息     * 如果飞行器接入多组电池，应该用此接口|
|返回值|ExtBatteryStateInfo（电池信息）|
|请求参数|index（电池组Index）
### getBatteryDamagedInfo
|方法名|getBatteryDamagedInfo|
| :--------  | :-----  |
|描述|* 获取电池故障信息|
|返回值|List<BatteryDamagedState>（返回电池故障信息列表）|
### getBatteryCriticalThreshold
|方法名|getBatteryCriticalThreshold|
| :--------  | :-----  |
|描述|* 设置电池电量严重不足时的阈值。这必须低于低阈值。该阈值通常会触发RTL。|
|返回值|void|
|请求参数|callback（callback）
### setBatteryCriticalThreshold
|方法名|setBatteryCriticalThreshold|
| :--------  | :-----  |
|描述|* 设置电池低电量返航电量阈值|
|返回值|void|
|请求参数|callback（callback）
|请求参数|threshold（电量百分比（0.00 - 0.30））
### getBatteryEmergencyThreshold
|方法名|getBatteryEmergencyThreshold|
| :--------  | :-----  |
|描述|* 设置电池危险电量低时的阈值。这必须低于临界阈值。这个阈值通常会触发着陆。|
|返回值|void|
|请求参数|callback（callback）
### setBatteryEmergencyThreshold
|方法名|setBatteryEmergencyThreshold|
| :--------  | :-----  |
|描述|* 设置电池低电量迫降阈值|
|返回值|void|
|请求参数|callback（callback）
|请求参数|threshold（电量百分比（0.00 - 0.30））
### getBatteryLowThreshold
|方法名|getBatteryLowThreshold|
| :--------  | :-----  |
|描述|* 设置电池电量低时的阈值。这必须高于临界阈值。|
|返回值|void|
|请求参数|callback（callback）
### setBatteryLowThreshold
|方法名|setBatteryLowThreshold|
| :--------  | :-----  |
|描述|* 设置电池低电量提醒阈值|
|返回值|void|
|请求参数|callback（callback）
|请求参数|threshold（电量百分比（0.00 - 0.50））
##INFO
### BatteryStateInfo
* 用于描述电池当前状态

|名称|描述|
| :--------  | :----:  |
|isBatteryDamaged|电池是否故障|
|batteryChargeState|电池充电状态|
|batteryTemperature|电池温度|
|totalVoltage|电池总电压|
|cellVoltage|电芯电压|
|batteryDischarge|放电电流cA|
|batteryChargeConsumed|电池剩余容量mAh|
|batteryEnergyConsumed|电池剩余能量hJ|
|batteryRemainingPercentage|电池剩余容量%|
|batteryRemainingTimes|电池剩余可用时间s|
### ExtBatteryStateInfo
* 用于描述电池硬件属性

|名称|描述|
| :--------  | :----:  |
|serialNumber|电池序列号|
|cellsInSeries|电池电芯数量|
|capacityFullSpecification|电池出厂设计容量|
|capacityFull|电池当前充满容量|
|cycleCount|电池循环次数|
|dischargeMinimumVoltage|电池最小放电电压|
|chargingMinimumVoltage|电池最小充电电压|
|chargingMaximumVoltage|电池最大充电电压|
|dischargeMaximumCurrent|电池最大放电电流|
##ENUM
### BatteryChargeState
* 无人机电池冲放电程度的状态枚举

|名称|值|描述|
| :--------  | :-----  | :----:  |
|BATTERY_CHARGE_STATE_UNDEFINED|0|不支持|
|BATTERY_CHARGE_STATE_OK|1|电池充电完成|
|BATTERY_CHARGE_STATE_LOW|2|电池电量状态低，关闭电池警告和信息监控|
|BATTERY_CHARGE_STATE_CRITICAL|3|电池状态严重故障，立即返回或中止。|
|BATTERY_CHARGE_STATE_EMERGENCY|4|电池状态紧急故障，立即返回或中止。|
|BATTERY_CHARGE_STATE_FAILED|5|电池故障，电池发生不可逆转损坏|
|BATTERY_CHARGE_STATE_UNHEALTHY|6|电池被诊断为有缺陷或发生错误，不鼓励/禁止使用|
|BATTERY_CHARGE_STATE_CHARGING|7|电池正在充电|
### BatteryDamagedState
* 无人机电池故障信息枚举

|名称|值|描述|
| :--------  | :-----  | :----:  |
|BATTERY_FAULT_DEEP_DISCHARGE,|-1|电池深度放电|
|BATTERY_FAULT_SPIKES,|-1|电池电压尖峰|
|BATTERY_FAULT_CELL_FAIL,|-1|电池电芯一个或多个单元出现故障|
|BATTERY_FAULT_OVER_CURRENT,|-1|过流故障|
|BATTERY_FAULT_OVER_TEMPERATURE,|-1|过温故障|
|BATTERY_FAULT_UNDER_TEMPERATURE,|-1|低温故障|
|BATTERY_FAULT_INCOMPATIBLE_VOLTAGE,|-1|无人机电压与电池电压不兼容|
|BATTERY_FAULT_INCOMPATIBLE_FIRMWARE,|-1|电池固件不兼容|
|BATTERY_FAULT_INCOMPATIBLE_CELLS_CONFIGURATION|-1|电池配置错误|
