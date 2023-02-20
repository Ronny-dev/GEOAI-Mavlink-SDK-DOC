### Documentation

#### `void setBatteryStateListener(IBatteryStateListener batteryStateListener)`

设置飞行器电池状态监听

* **See also:** BatteryStateInfo
* **Parameters:** `batteryStateListener` — 电池回调

#### `ExtBatteryStateInfo getBatteryExtraInfo()`

获取电池额外提供的信息

* **Returns:** 电池信息
* **See also:** ExtBatteryStateInfo

#### `ExtBatteryStateInfo getBatteryExtraInfo(int index)`

获取电池额外提供的信息 如果飞行器接入多组电池，应该用此接口

* **Parameters:** `index` — 电池组Index
* **Returns:** 电池信息

#### `List<BatteryDamagedState> getBatteryDamagedInfo()`

获取电池故障信息

* **Returns:** 返回电池故障信息列表

#### `void getBatteryCriticalThreshold(@NonNull CompletionCallback.ICompletionCallbackWith<Float> callback)`

设置电池电量严重不足时的阈值。这必须低于低阈值。该阈值通常会触发RTL。

* **Parameters:** `callback` — callback

#### `void setBatteryCriticalThreshold(float threshold, CompletionCallback.ICompletionCallback callback)`

设置电池低电量返航电量阈值

* **Parameters:**
    * `threshold` — 电量百分比（0.00 - 0.30）
    * `callback` — callback

#### `void getBatteryEmergencyThreshold(@NonNull CompletionCallback.ICompletionCallbackWith<Float> callback)`

设置电池危险电量低时的阈值。这必须低于临界阈值。这个阈值通常会触发着陆。

* **Parameters:** `callback` — callback

#### `void setBatteryEmergencyThreshold(float threshold, CompletionCallback.ICompletionCallback callback)`

设置电池低电量迫降阈值

* **Parameters:**
    * `threshold` — 电量百分比（0.00 - 0.30）
    * `callback` — callback

#### `void getBatteryLowThreshold(@NonNull CompletionCallback.ICompletionCallbackWith<Float> callback)`

设置电池电量低时的阈值。这必须高于临界阈值。

* **Parameters:** `callback` — callback

#### `void setBatteryLowThreshold(float threshold, CompletionCallback.ICompletionCallback callback)`

设置电池低电量提醒阈值

* **Parameters:**
    * `threshold` — 电量百分比（0.00 - 0.50）
    * `callback` — callback