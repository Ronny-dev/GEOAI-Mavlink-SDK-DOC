### Documentation

#### `void updateParameterFromDrone(CompletionCallback.ICompletionCallback callback) throws IOException`

从无人机下载实时参数列表（非参数数据）

* **Parameters:** `callback` — callback
* **Exceptions:** `IOException` — IOException

#### `void readAllParameter(IAllParameterSyncListener listener)`

读取飞控参数列表全部数据, 其中包含飞控算法核心参数

* **Parameters:** `listener` — listener

#### `void readSingleParameter(int index, ISingleParameterSyncListener listener)`

通过序列index读取飞控参数列表单个属性

* **Parameters:**
    * `index` — 需要读取的index
    * `listener` — listener

#### `void writeSingleParameter(ParamValueInfo info, CompletionCallback.ICompletionCallback callback)`

修改某项飞控参数属性；参数内包含飞控核心算法，修改前请确认参数是否正确

* **Parameters:**
    * `info` — 修改参数的属性
    * `callback` — callback

#### `void setTransmitRateListener(ITransmitRateListener listener)`

获取当前GCS系统数传实时传输速率

* **Parameters:** `listener` — listener

#### `void fetchFlightLogList(IFetchFlightLogListListener listener)`

获取飞行器日志列表

* **Parameters:** `listener` — listener

#### `void fetchFlightLog(FlightLogEntryInfo info, String saveFilePath, @NonNull IFlightLogDownloadListener listener)`

通过指定的entry下载飞行器日志

* **Parameters:**
    * `info` — 请先通过{{@link #fetchFlightLogList(IFetchFlightLogListListener)}获取文件列表}
    * `saveFilePath` — 日志文件下载保存的路径
    * `listener` — listener

#### `void cancelFetchFlightLog()`

取消飞行器日志文件下载的动作 成功调用后会通过{@link IFlightLogDownloadListener}返回取消指令码

#### `void ftpFileList(String filePath, CompletionCallback.ICompletionCallbackWith<ArrayList<MFTPManager.FileDirectoryList>> listener)`

文件传输 - 展示飞控指定目录下文件

* **Parameters:**
    * `filePath` — 飞控内部路径
    * `listener` — listener

#### `void ftpDelFile(String filePath, CompletionCallback.ICompletionCallback callback)`

文件传输 - 删除飞控内部指定文件

* **Parameters:**
    * `filePath` — 需删除的文件路径
    * `callback` — callback

#### `void ftpDelDirectory(String filePath, CompletionCallback.ICompletionCallback callback)`

文件传输 - 删除飞控内部指定文件夹

* **Parameters:**
    * `filePath` — 需删除的文件夹路径
    * `callback` — callback

#### `void ftpCreateDirectory(String filePath, CompletionCallback.ICompletionCallback callback)`

文件传输 - 在飞控内部创建文件夹

* **Parameters:**
    * `filePath` — 需要创建的文件夹路径
    * `callback` — callback

#### `void ftpCalcFileCrc32(String filePath, CompletionCallback.ICompletionCallbackWith<short[]> listener)`

文件传输 - 生成文件CRC32校验码

* **Parameters:**
    * `filePath` — 文件路径
    * `listener` — listener

#### `void ftpDownloadFile(String filePath, IFtpFileDownloadListener listener)`

文件传输 - 下载飞控存储系统内部文件

* **Parameters:**
    * `filePath` — 文件路径
    * `listener` — listener

#### `void ftpUploadFile(String uploadFilePath, String saveFilePath, IFtpFileUploadListener listener)`

文件传输 - 上传文件到飞控存储指定文件夹

* **Parameters:**
    * `uploadFilePath` — 上传文件的完整路径
    * `saveFilePath` — 保存文件路径
    * `listener` — listener

#### `void ftpTerminateControl(CompletionCallback.ICompletionCallback callback)`

文件传输 - 终止[上传\下载]相关操作

* **Parameters:** `callback` — callback