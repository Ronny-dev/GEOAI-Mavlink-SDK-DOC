# 日志获取指南

### 写在前面

---

为了满足用户用户对于下位机（飞行控制器、机载电脑）的日志获取需求，SDK实现了Mavlink系统中的日志获取协议。用户无需关心Mavlink底层复杂的日志获取逻辑，仅需调用相关的接口，便可以将日志文件下载保存至指定的目录。

目前使用Mavlink日志管理系统有如下优点：

1. 允许非常安全的远程数据处理
2. 支持添加不同类型的插件
3. 具有良好的流体性和传输特性

缺点：

1. 数据吞吐量较低

### 提供的接口

---

```java
     /**
 * 获取飞行器日志列表
 * @param listener listener
 */
    void fetchFlightLogList(IFetchFlightLogListListener listener);

            /**
             * 通过指定的entry下载飞行器日志
             * @param info 请先通过{{@link #fetchFlightLogList(IFetchFlightLogListListener)}获取文件列表}
             * @param saveFilePath 日志文件下载保存的路径
             * @param listener listener
             */
            void fetchFlightLog(FlightLogEntryInfo info, String saveFilePath, @NonNull IFlightLogDownloadListener listener);

        /**
         * 取消飞行器日志文件下载的动作
         * 成功调用后会通过{@link IFlightLogDownloadListener}返回取消指令码
         */
        void cancelFetchFlightLog();
```

### 流程设计

---

- 用户在日志下载时传入的FlightLogEntryInfo 必须是文件列表中获取的
- saveFilePath中已经处理了文件名的操作，需要提供完整文件路径，SDK会进行文件创建操作
- 用户可以在IFlightLogDownloadListener 中进行下载进度的监听
- 错误码在IFlightLogDownloadListener 中，按枚举进行解析即可

### 错误码

---

```java
    // Error Code.
private static final int ERR_CODE_FILE_PATH_INVALID         = -1001;
private static final int ERR_CODE_DOWNLOAD_DESC_INVALID     = -1002;
private static final int ERR_CODE_DOWNLOAD_BLOCK_EMPTY      = -1003;
private static final int ERR_CODE_LOGGER_FILE_NOT_CREATE    = -1004;
```

### 日志分析

---

用户在通过上述的接口下载日志文件后，可以通过PX4提供的飞行日志分析软件进行日志分析。
若果日志分析工具无法正确打开日志文件，请确保日志文件被正确下载。
![flight_review](https://docs.px4.io/main/assets/img/flight_modes.0e6a26db.png)
关于日志分析工具的具体使用方式，可以访问PX4Tools-Log Analysis Flight Review进行资料查阅
[Log Analysis using Flight Review](https://docs.px4.io/main/en/log/flight_review.html)

### 参考文件

---

[FlightLogDownloadManager.java](https://github.com/Ronny-dev/GeoaiMavLink_Android)

[MavlinkProtocol](https://mavlink.io/en/messages/common.html#LOG_REQUEST_LIST)

[日志分析](https://docs.px4.io/main/zh/dev_log/flight_log_analysis.html)