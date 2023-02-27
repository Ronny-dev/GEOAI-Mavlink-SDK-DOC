# 文件管理指南

### 写在前面

---

MavLink文件管理协议（MFTP）是一种专为管理文件而设计的安全协议。它可以实现文件的上传、下载和检查功能，支持用户访问和更新文件。此协议采用安全的压缩技术，可减少文件大小，帮助用户更快捷地传输文件。此外，它还可以在传输过程中提供数据加密和验证程序，确保文件安全传输。此协议可以帮助用户更有效地管理文件，例如通过提供合理的文件访问控制来实现文件共享和差异更新；并为文件管理提供必要的工具，以自动存储、组织和检索文件。因此，MavLink文件管理协议可以提高文件管理的效率并有效地保护文件安全。

### 使用方式

---

用户可以通过MFTP接口获取飞行控制器或者机载电脑的内部存储执行控制权，可以进行底层的文件交互操作。请不要随意对FC的内部空间进行读写，如果文件被错误删除，有可能导致FC、飞行电脑永久变砖。

### 提供的接口

---

在SDK中实现了MFTP如下控制指令：

- TERMINATE_SESSION
- LIST_DIRECTORY
- OPEN_FILE
- READ_FILE
- CREATE_FILE
- WRITE_FILE
- CREATE_DIRECTORY
- REMOVE_DIRECTORY
- CALC_CRC32

> SDK已经对上面指令进行相应的封装，暴露API层具体如下
>

在SDK中暴露的API接口：

```java
    /**
     * 文件传输 - 展示飞控指定目录下文件
     * @param filePath 飞控内部路径
     * @param listener listener
     */
    void ftpFileList(String filePath, CompletionCallback.ICompletionCallbackWith<ArrayList<MFTPManager.FileDirectoryList>> listener);

    /**
     * 文件传输 - 删除飞控内部指定文件
     * @param filePath 需删除的文件路径
     * @param callback callback
     */
    void ftpDelFile(String filePath, CompletionCallback.ICompletionCallback callback);

    /**
     * 文件传输 - 删除飞控内部指定文件夹
     * @apiNote 非递归删除，请确保文件夹内部无占用文件
     * @param filePath 需删除的文件夹路径
     * @param callback callback
     */
    void ftpDelDirectory(String filePath, CompletionCallback.ICompletionCallback callback);

    /**
     * 文件传输 - 在飞控内部创建文件夹
     * @param filePath 需要创建的文件夹路径
     * @param callback callback
     */
    void ftpCreateDirectory(String filePath, CompletionCallback.ICompletionCallback callback);

    /**
     * 文件传输 - 生成文件CRC32校验码
     * @param filePath 文件路径
     * @param listener listener
     */
    void ftpCalcFileCrc32(String filePath, CompletionCallback.ICompletionCallbackWith<short[]> listener);

    /**
     * 文件传输 - 下载飞控存储系统内部文件
     * @param filePath 文件路径
     * @param listener listener
     */
    void ftpDownloadFile(String filePath, IFtpFileDownloadListener listener);

    /**
     * 文件传输 - 上传文件到飞控存储指定文件夹
     * @param uploadFilePath 上传文件的完整路径
     * @param saveFilePath 保存文件路径
     * @param listener listener
     */
    void ftpUploadFile(String uploadFilePath, String saveFilePath, IFtpFileUploadListener listener);

    /**
     * 文件传输 - 终止[上传\下载]相关操作
     * @param callback callback
     */
    void ftpTerminateControl(CompletionCallback.ICompletionCallback callback);
```

### 参考文件

---

[MFTP](https://mavlink.io/en/services/ftp.html)

[Mavlink Common Protocol](https://mavlink.io/en/messages/common.html#FILE_TRANSFER_PROTOCOL)