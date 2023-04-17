### updateParameterFromDrone
|方法名|updateParameterFromDrone|
| :--------  | :-----  |
|描述|* 从无人机下载实时参数列表（非参数数据）|
|返回值|void|
|请求参数|callback（callback）
|throws|IOException|
### readAllParameter
|方法名|readAllParameter|
| :--------  | :-----  |
|描述|* 读取飞控参数列表全部数据, 其中包含飞控算法核心参数|
|返回值|void|
|请求参数|listener（listener）
### readSingleParameter
|方法名|readSingleParameter|
| :--------  | :-----  |
|描述|* 通过序列index读取飞控参数列表单个属性|
|返回值|void|
|请求参数|listener（listener）
|请求参数|index（需要读取的index）
### writeSingleParameter
|方法名|writeSingleParameter|
| :--------  | :-----  |
|描述|* 修改某项飞控参数属性；参数内包含飞控核心算法，修改前请确认参数是否正确|
|返回值|void|
|请求参数|callback（callback）
|请求参数|info（修改参数的属性）
### setTransmitRateListener
|方法名|setTransmitRateListener|
| :--------  | :-----  |
|描述|* 获取当前GCS系统数传实时传输速率|
|返回值|void|
|请求参数|listener（listener）
### fetchFlightLogList
|方法名|fetchFlightLogList|
| :--------  | :-----  |
|描述|* 获取飞行器日志列表|
|返回值|void|
|请求参数|listener（listener）
### fetchFlightLog
|方法名|fetchFlightLog|
| :--------  | :-----  |
|描述|* 通过指定的entry下载飞行器日志|
|返回值|void|
|请求参数|listener（listener）
|请求参数|saveFilePath（日志文件下载保存的路径）
|请求参数|info（请先通过{{link #fetchFlightLogList(IFetchFlightLogListListener)}获取文件列表}）
### cancelFetchFlightLog
|方法名|cancelFetchFlightLog|
| :--------  | :-----  |
|描述|* 取消飞行器日志文件下载的动作|
|返回值|void|
|成功调用后会通过{link|IFlightLogDownloadListener}返回取消指令码|
### ftpFileList
|方法名|ftpFileList|
| :--------  | :-----  |
|描述|* 文件传输 - 展示飞控指定目录下文件|
|返回值|void|
|请求参数|filePath（飞控内部路径）
|请求参数|listener（listener）
### ftpDelFile
|方法名|ftpDelFile|
| :--------  | :-----  |
|描述|* 文件传输 - 删除飞控内部指定文件|
|返回值|void|
|请求参数|filePath（需删除的文件路径）
|请求参数|callback（callback）
### ftpDelDirectory
|方法名|ftpDelDirectory|
| :--------  | :-----  |
|描述|* 文件传输 - 删除飞控内部指定文件夹|
|返回值|void|
|请求参数|filePath（需删除的文件夹路径）
|请求参数|callback（callback）
|apiNote|非递归删除，请确保文件夹内部无占用文件|
### ftpCreateDirectory
|方法名|ftpCreateDirectory|
| :--------  | :-----  |
|描述|* 文件传输 - 在飞控内部创建文件夹|
|返回值|void|
|请求参数|filePath（需要创建的文件夹路径）
|请求参数|callback（callback）
### ftpCalcFileCrc32
|方法名|ftpCalcFileCrc32|
| :--------  | :-----  |
|描述|* 文件传输 - 生成文件CRC32校验码|
|返回值|void|
|请求参数|filePath（文件路径）
|请求参数|listener（listener）
### ftpDownloadFile
|方法名|ftpDownloadFile|
| :--------  | :-----  |
|描述|* 文件传输 - 下载飞控存储系统内部文件|
|返回值|void|
|请求参数|filePath（文件路径）
|请求参数|listener（listener）
### ftpUploadFile
|方法名|ftpUploadFile|
| :--------  | :-----  |
|描述|* 文件传输 - 上传文件到飞控存储指定文件夹|
|返回值|void|
|请求参数|listener（listener）
|请求参数|uploadFilePath（上传文件的完整路径）
|请求参数|saveFilePath（保存文件路径）
### ftpTerminateControl
|方法名|ftpTerminateControl|
| :--------  | :-----  |
|描述|* 文件传输 - 终止[上传\下载]相关操作|
|返回值|void|
|请求参数|callback（callback）
##INFO
### FlightLogEntryInfo
* 飞控日志

|名称|描述|
| :--------  | :----:  |
|id|飞行器日志序列ID|
|timestamp|飞行器日志最后写入时间|
|size|飞行器日志大小|
### null

|名称|描述|
| :--------  | :----:  |
### null

|名称|描述|
| :--------  | :----:  |
### LinkNodeTransmitRateInfo
* 无线电链路上下行速率统计

|名称|描述|
| :--------  | :----:  |
|0|速率统计回调的时间戳|
|0|地面站数传上行速率|
|0|地面站数传下行速率|
### null

|名称|描述|
| :--------  | :----:  |
### null

|名称|描述|
| :--------  | :----:  |
### null

|名称|描述|
| :--------  | :----:  |
### null

|名称|描述|
| :--------  | :----:  |
|-1|参数序列|
|Float.NaN|参数值|
|ParamValueTypeState.MAV_PARAM_TYPE_INT8|参数类型|
|""|参数名|
|null|参数描述|
### null

|名称|描述|
| :--------  | :----:  |
##ENUM
