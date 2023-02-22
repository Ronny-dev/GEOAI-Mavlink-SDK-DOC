### Documentation

#### `void setAirLinkStateListener(IAirLinkStateListener listener)`

设置地面电台模块监听回调{@link com.geoai.mavlink.util.MeshHelper2.MeshStatus}

* **Parameters:** `listener` — listener

#### `void isAirLinkConnected(CompletionCallback.ICompletionCallbackWith<Boolean> callback)`

获取当前地面电台是否正常连接

* **Parameters:** `callback` — callback

#### `void getHardwareAirLinkVersion(CompletionCallback.ICompletionCallbackWith<String> callback)`

获取地面电台硬件版本号

* **Parameters:** `callback` — callback

#### `void getAirLinkSerialNumber(CompletionCallback.ICompletionCallbackWith<String> callback)`

获取地面电台序列号

* **Parameters:** `callback` —

#### `void airLinkRestart(CompletionCallback.ICompletionCallback callback)`

地面电台重启

* **Parameters:** `callback` — callback

#### `void enterPairMode(IAirLinkPairListener listener)`

进入对频模式

* **Parameters:** `listener` — callback

#### `void exitPairMode(CompletionCallback.ICompletionCallback callback)`

退出对频模式

* **Parameters:** `callback` — callback