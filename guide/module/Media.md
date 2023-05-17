# 媒体系统

## 媒体系统逻辑与实现过程

目前目录和文件生成规则如下图所示：

![Untitled](https://imgs.wiki/imgs/2023/05/17/93212d49444b8cb5.png)

### 自组网系统

无人机在飞行过程中，拍摄的图片和录制的视频会在**媒体生成结束后自动被云冠检测并实时进行下载**。正常情况下飞机在降落到地面之后，媒体视频已经被完整下载在云冠的指定目录内。这时候用户只需要调用MavSDK相关的媒体下载接口就可以将媒体数据下载下来。

![Untitled](https://imgs.wiki/imgs/2023/05/17/31dfa93c23f32e31.png)

### 自研飞控系统

与自组网系统基本一致；在无人机飞行过程中，生成的媒体素材均会存储在云冠的指定目录内。这时候用户只需要调用MavSDK相关的媒体下载接口就可以将媒体数据下载下来。

![Untitled](https://imgs.wiki/imgs/2023/05/17/e7a83b4e23065cac.png)

### 如何使用

1. 首先用户需要拿到媒体组件：

```java
StarLinkClientManager.getInstance().getProduct(droneID).getMediaManager();
```

1. 需要获取目录（架次）详细信息

```java
mediaManager.getFolderList(new CompletionCallback.ICompletionCallbackWith<List<MediaFolderInfo>>(){
    @Override
    public void onFailure(GEOAIError geoaiError){
        //todo onFailure
    }

    @Override
    public void onResult(List<MediaFolderInfo> mediaFolderInfos){
        //todo success
    }
});
```

1. 根据步骤二中获取到的目录（架次）信息，去获取该目录（架次）的媒体文件详情；用户也可以指定媒体类型和相机类型进行检索获取；

MediaFileFormatType

- *`ALL`(全部)*
- *`PHOTO`（照片）*
- *`VIDEO`（视频）*

MediaFileCameraType

- *`ALL`（全部）*
- *`WIDE`（广角）*
- *`ZOOM`（变焦）*
- *`THERMAL`（红外）*
- *`HYBRID`（混合）*

```java
//获取全部
mediaManager.getMediaList(folderInfo, new CompletionCallback.ICompletionCallbackWith<List<MediaInfo>>() {
    @Override
    public void onFailure(GEOAIError geoaiError) {
				//todo onFailure
    }

    @Override
    public void onResult(List<MediaInfo> mediaInfos) {
				//todo success
    }
});
//检索获取
mediaManager.getMediaList(mediaInfo, MediaFileFormatType.ALL, MediaFileCameraType.ALL, new CompletionCallback.ICompletionCallbackWith<List<MediaInfo>>() {
    @Override
    public void onFailure(GEOAIError geoaiError) {
				//todo onFailure
    }

    @Override
    public void onResult(List<MediaInfo> mediaInfos) {
				//todo success
    }
});
```

至此，已经可以获取到媒体信息的下载地址。用户需要拼接出下载地址进行http下载。在媒体详情中可以进行如下类型拼接：

1. 原图地址：getOriginPath
2. 缩略图地址：getThumbnailPath
3. icon图地址：getIconPath
1. 拼接下载地址

```java
"http://" + mediaManager.getComponentConst().getUdpIpAddr() + ":8000/" + mediaInfo.getOriginPath();
```

用户在获取到目录（架次）信息后，可以直接进行压缩包全量下载；压缩包内会存有该目录（架次）的所有媒体信息。

1. 下载指定目录（架次）全部媒体素材（压缩包）

```java
URL archiveZip = mediaManager.getArchiveZip(mediaInfo);
```

### 4G媒体下载

在P2P组件正常工作的情况下，可以使用如下接口通过云冠4G上传的形式进行媒体下载

> 这个过程会花费大量的流量，建议仅做缩略图的下载并做好充足的提示。
>

```java
mediaManager.downloadMediaFromP2pTranslate(mediaInfo, new File("file to save"), new IMediaP2pDownloadListener() {
    @Override
    public void onResult(boolean isSuccess, GEOAIError geoaiError) {
				//todo onFailure
    }
    
    @Override
    public void onPercent(float percent) {
				//todo download percent.
    }
});
```

### 示例程序

开发者可以通过[示例程序](https://github.com/Ronny-dev/GCS)，学习媒体组件的调用逻辑和展示形式

![Untitled](https://imgs.wiki/imgs/2023/05/17/7065494a50dcc019.gif)
