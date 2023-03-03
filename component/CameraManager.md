### Documentation

#### `void setCameraHardwareStateListener(ICameraHardwareState listener)`

设置相机硬件状态

* **Parameters:** `listener` — listener

#### `void setCameraSystemStateListener(ICameraSystemState listener)`

设置相机系统状态

* **Parameters:** `listener` — listener

#### `void setCameraNewGeneratedInfoCallback(ICameraNewGeneratedInfoListener listener)`

设置相机生成新媒体文件的回调

#### `void setRecognizeStateListener(IRecognizeStateListener listener)`

设置机载电脑图像识别结果回调

* **Parameters:** `listener` — listener

#### `void startSingleCapture(CompletionCallback.ICompletionCallback callback)`

触发相机拍照(单张)

* **Parameters:** `callback` — callback

#### `void startComboCapture(int count, CompletionCallback.ICompletionCallback callback)`

触发相机拍照(多张连拍)

* **Parameters:**
    * `count` — 连拍数量
    * `callback` — callback

#### `void startIntervalCapture(int interval, CompletionCallback.ICompletionCallback callback)`

触发相机定时拍照

* **Parameters:**
    * `interval` — 频率 unit s
    * `callback` — callback

#### `void stopIntervalCapture(CompletionCallback.ICompletionCallback callback)`

触发相机停止定时拍照

* **Parameters:** `callback` — callback

#### `void startRecord(CompletionCallback.ICompletionCallback callback)`

触发相机启动录像

* **Parameters:** `callback` — callback

#### `void stopRecord(CompletionCallback.ICompletionCallback callback)`

触发相机停止录像

* **Parameters:** `callback` — callback

#### `void setCameraMode(CameraMode mode, CompletionCallback.ICompletionCallback callback)`

改变相机当前模式

* **Parameters:**
    * `mode` — {@link CameraMode} image/video
    * `callback` — callback

#### `void setZoomRatio(CameraZoomRatio ratio, CompletionCallback.ICompletionCallback callback)`

设置相机变焦倍率

* **Parameters:**
    * `ratio` — {@link CameraZoomRatio} x1/x2/x3
    * `callback` — callback

#### `void setFocusRing(boolean isAuto, int ring, CompletionCallback.ICompletionCallback callback)`

设置相机对焦环属性

* **Parameters:**
    * `isAuto` — 是否启动自动对焦
    * `ring` — 对焦环属性(0-50)
    * `callback` — callback

#### `void setISO(CameraISO iso, CompletionCallback.ICompletionCallback callback)`

设置相机ISO参数

* **Parameters:**
    * `iso` — {@link CameraISO} 100-6400
    * `callback` — callback

#### `void setAperture(CameraAperture aperture, CompletionCallback.ICompletionCallback callback)`

设置相机光圈参数

* **Parameters:**
    * `aperture` — 光圈{@link CameraAperture}
    * `callback` — callback

#### `void setShutterSpeed(CameraShutterSpeed shutterSpeed, CompletionCallback.ICompletionCallback callback)`

设置相机快门参数

* **Parameters:**
    * `shutterSpeed` — 快门{@link CameraShutterSpeed}
    * `callback` — callback

#### `void setExposure(CameraExposure exposure, CompletionCallback.ICompletionCallback callback)`

设置相机曝光参数

* **Parameters:**
    * `exposure` — 曝光{@link CameraExposure}
    * `callback` — callback

#### `void resetCameraConfigure(CompletionCallback.ICompletionCallback callback)`

重置相机所有参数

* **Parameters:** `callback` — callback