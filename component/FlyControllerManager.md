### Documentation

#### `void setFlyControllerStateListener(IFlyControllerStateListener listener)`

设置飞行器状态监听{@link com.geoai.mavlink.geoainet.flycontroller.info.FlyControllerStateInfo}

* **Parameters:** `listener` — listener

#### `void setDiagnosticsStateListener(IDiagnosticsStateListener listener)`

设置飞行器HMS系统状态监听回调（健康管理系统）

* **Parameters:** `listener` — listener

#### `void startAircraftTakeoff(CompletionCallback.ICompletionCallback callback)`

发送无人机起飞指令；无人机会起飞到1.2m后悬停

* **Parameters:** `callback` — callback

#### `void startAircraftTakeoff(float altitude, CompletionCallback.ICompletionCallback callback)`

发送无人机起飞指令

* **Parameters:**
    * `altitude` — 起飞悬停高度
    * `callback` — callback

#### `void startAircraftLand(CompletionCallback.ICompletionCallback callback)`

发送无人机降落指令

* **Parameters:** `callback` — callback

#### `void stopAircraftLand(CompletionCallback.ICompletionCallback callback)`

发送无人机取消降落指令

* **Parameters:** `callback` — callback

#### `void startAircraftGoHome(CompletionCallback.ICompletionCallback callback)`

发送无人机返航指令；无人机会先升高到返航高度后返航

* **Parameters:** `callback` — callback

#### `void stopAircraftGoHome(CompletionCallback.ICompletionCallback callback)`

发送无人机取消返航指令

* **Parameters:** `callback` — callback

#### `void setGoHomeAltitude(int altitude, CompletionCallback.ICompletionCallback callback)`

设置无人机返航高度

* **Parameters:**
    * `altitude` — 返航高度
    * `callback` — callback

#### `void getGoHomeAltitude(CompletionCallback.ICompletionCallbackWith<Integer> callback)`

获取无人机返航高度

* **Parameters:** `callback` — callback

#### `void getGoHomeLocation(CompletionCallback.ICompletionCallbackWith<double[]> callback)`

获取无人机当前返航点坐标

* **Parameters:** `callback` — callback

#### `void stopAllAction(CompletionCallback.ICompletionCallback callback)`

终止飞行器动作指令并悬停

* **Parameters:** `callback` — callback

#### `void startForceLanding(CompletionCallback.ICompletionCallback callback)`

发送无人机强制降落（不会进入视觉降落程序）

* **Parameters:** `callback` — callback

#### `void setDroneArm(CompletionCallback.ICompletionCallback callback)`

飞机上锁

* **Parameters:** `callback` — callback

#### `void setDroneDisarm(CompletionCallback.ICompletionCallback callback)`

飞机解锁

* **Parameters:** `callback` — callback

#### `void setJoyStickEnable(boolean isEnable, CompletionCallback.ICompletionCallback callback)`

飞行器启动虚拟摇杆

* **Parameters:** `callback` — callback

#### `void sendJoyStickControl(short x, short y, short z, short r, CompletionCallback.ICompletionCallback callback)`

发送虚拟摇杆指令（美国手）

* **Parameters:**
    * `x` — pitch
    * `y` — roll
    * `z` — throttle
    * `r` — yaw
    * `callback` — callback