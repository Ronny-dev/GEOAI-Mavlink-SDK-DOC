### getCameraVideoStreamSource
|方法名|getCameraVideoStreamSource|
| :--------  | :-----  |
|描述|* 获取相机视频源|
|返回值|void|
|请求参数|listener（listener）
|云冠|支持|
### setCameraVideoStreamSource
|方法名|setCameraVideoStreamSource|
| :--------  | :-----  |
|描述|* 设置相机视频源|
|返回值|void|
|请求参数|listener（listener）
|请求参数|source（视频源）
|云冠|支持|
### getCameraVideoStreamResolution
|方法名|getCameraVideoStreamResolution|
| :--------  | :-----  |
|描述|* 获取相机视频流分辨率|
|返回值|void|
|请求参数|listener（listener）
|云冠|支持|
### setCameraVideoStreamResolution
|方法名|setCameraVideoStreamResolution|
| :--------  | :-----  |
|描述|* 设置相机视频流分辨率|
|返回值|void|
|请求参数|listener（listener）
|请求参数|resolution（分辨率）
|云冠|支持|
### getCameraVideoStreamBitrate
|方法名|getCameraVideoStreamBitrate|
| :--------  | :-----  |
|描述|* 获取相机视频流比特率|
|返回值|void|
|请求参数|listener（listener）
|云冠|支持|
### setCameraVideoStreamBitrate
|方法名|setCameraVideoStreamBitrate|
| :--------  | :-----  |
|描述|* 设置相机视频流比特率|
|返回值|void|
|请求参数|listener（listener）
|请求参数|bitrate（比特率）
|云冠|支持|
### getCameraName
|方法名|getCameraName|
| :--------  | :-----  |
|描述|* 获取相机名称|
|返回值|void|
|请求参数|listener（listener）
|云冠|支持|
### setCameraHardwareStateListener
|方法名|setCameraHardwareStateListener|
| :--------  | :-----  |
|描述|* 设置相机硬件状态|
|返回值|void|
|请求参数|listener（listener）
|云冠|不支持|
### setCameraSystemStateListener
|方法名|setCameraSystemStateListener|
| :--------  | :-----  |
|描述|* 设置相机系统状态|
|返回值|void|
|请求参数|listener（listener）
|云冠|不支持|
### setCameraNewGeneratedInfoCallback
|方法名|setCameraNewGeneratedInfoCallback|
| :--------  | :-----  |
|描述|* 设置相机生成新媒体文件的回调|
|返回值|void|
|请求参数|listener（listener）
|云冠|不支持|
### setRecognizeStateListener
|方法名|setRecognizeStateListener|
| :--------  | :-----  |
|描述|* 设置机载电脑图像识别结果回调|
|返回值|void|
|请求参数|listener（listener）
|云冠|不支持|
### startSingleCapture
|方法名|startSingleCapture|
| :--------  | :-----  |
|描述|* 触发相机拍照(单张)|
|返回值|void|
|请求参数|callback（callback）
|云冠|支持|
### startComboCapture
|方法名|startComboCapture|
| :--------  | :-----  |
|描述|* 触发相机拍照(多张连拍)|
|返回值|void|
|请求参数|count（连拍数量）
|请求参数|callback（callback）
|云冠|不支持|
### startIntervalCapture
|方法名|startIntervalCapture|
| :--------  | :-----  |
|描述|* 触发相机定时拍照|
|返回值|void|
|请求参数|callback（callback）
|请求参数|interval（频率 unit s）
|云冠|支持|
### stopIntervalCapture
|方法名|stopIntervalCapture|
| :--------  | :-----  |
|描述|* 触发相机停止定时拍照|
|返回值|void|
|请求参数|callback（callback）
|云冠|支持|
### startRecord
|方法名|startRecord|
| :--------  | :-----  |
|描述|* 触发相机启动录像|
|返回值|void|
|请求参数|callback（callback）
|云冠|支持|
### stopRecord
|方法名|stopRecord|
| :--------  | :-----  |
|描述|* 触发相机停止录像|
|返回值|void|
|请求参数|callback（callback）
|云冠|支持|
### setCameraMode
|方法名|setCameraMode|
| :--------  | :-----  |
|描述|* 改变相机当前模式|
|返回值|void|
|请求参数|mode（{link CameraMode} image/video）
|请求参数|callback（callback）
|云冠|支持|
### getCameraMode
|方法名|getCameraMode|
| :--------  | :-----  |
|描述|* 获取相机当前模式|
|返回值|void|
|请求参数|callback（callback）
|云冠|支持|
### setZoomRatio
|方法名|setZoomRatio|
| :--------  | :-----  |
|描述|* 设置相机变焦倍率|
|返回值|void|
|请求参数|callback（callback）
|请求参数|ratio（ratio）
|云冠|支持|
### getZoomRatio
|方法名|getZoomRatio|
| :--------  | :-----  |
|描述|* 获取相机电子变焦倍率|
|返回值|void|
|请求参数|callback（callback）
|云冠|支持|
### setFocusRing
|方法名|setFocusRing|
| :--------  | :-----  |
|描述|* 设置相机对焦环属性|
|返回值|void|
|请求参数|ring（对焦环属性(0-50)）
|请求参数|isAuto（是否启动自动对焦）
|请求参数|callback（callback）
|云冠|不支持|
### getFocusRing
|方法名|getFocusRing|
| :--------  | :-----  |
|描述|* 获取相机对焦环属性|
|返回值|void|
|请求参数|callback（callback）
|云冠|不支持|
### setISO
|方法名|setISO|
| :--------  | :-----  |
|描述|* 设置相机ISO参数|
|返回值|void|
|请求参数|iso（{link CameraISO} 100-6400）
|请求参数|callback（callback）
|云冠|不支持|
### setAperture
|方法名|setAperture|
| :--------  | :-----  |
|描述|* 设置相机光圈参数|
|返回值|void|
|请求参数|aperture（光圈{link CameraAperture}）
|请求参数|callback（callback）
|云冠|不支持|
### setShutterSpeed
|方法名|setShutterSpeed|
| :--------  | :-----  |
|描述|* 设置相机快门参数|
|返回值|void|
|请求参数|callback（callback）
|请求参数|shutterSpeed（快门{link CameraShutterSpeed}）
|云冠|不支持|
### setExposure
|方法名|setExposure|
| :--------  | :-----  |
|描述|* 设置相机曝光参数|
|返回值|void|
|请求参数|exposure（曝光{link CameraExposure}）
|请求参数|callback（callback）
|云冠|不支持|
### resetCameraConfigure
|方法名|resetCameraConfigure|
| :--------  | :-----  |
|描述|* 重置相机所有参数|
|返回值|void|
|请求参数|callback（callback）
|云冠|支持|

##INFO
### CameraHardwareInfo
 * 相机硬件属性

|名称|描述|
| :--------  | :----:  |
|resolutionHeight|相机当前画幅Height|
|resolutionWidth|相机当前画幅Width|
|CameraMode.CAMERA_MODE_IMAGE|相机当前模式|
|1.0f|相机当前变焦倍率|
|CameraISO.CAMERA_ISO_AUTO|ISO|
|CameraShutterSpeed.CAMERA_MANAGER_SHUTTER_SPEED_UNKNOWN|快门|
|CameraAperture.CAMERA_APERTURE_F_UNKNOWN|光圈|
|CameraExposure.CAMERA_EXPOSURE_COMPENSATION_N_0_0|曝光|
|cameraFocusRing|对焦环参数|
### CameraNewGeneratedInfo
 * 相机新媒体文件生成类型

|名称|描述|
| :--------  | :----:  |
|index|媒体序列|
|latitude|纬度|
|longitude|经度|
|altitude|高度|
|path|存储路径|
### CameraSystemInfo
 * 相机系统属性

|名称|描述|
| :--------  | :----:  |
|CameraImageStatus.CAMERA_IMAGE_UNKNOWN|相机拍照状态|
|CameraVideoStatus.CAMERA_VIDEO_UNKNOWN|相机录像状态|
|imageIntervalUnit|相机定时拍照参数|
|recordingTimeMs|相机录制时长|
|availableCapacity|相机剩余存储可拍摄数量|
### RecognizeStateInfo
 * 机载电脑识别对象返回类型

|名称|描述|
| :--------  | :----:  |
|x|The x coordinate of the object in the graph|
|y|The y coordinate of the object in the graph|
|width|The actual pixel width of the object|
|height|Actual pixel height of the object|
|order_num|object order num|
|frame_id|frame id|
|total_num|object total num|
|name|Identified target name|

##ENUM
### CameraAperture
 * 相机光圈

|名称|值|描述|
| :--------  | :-----  | :----:  |
|CAMERA_APERTURE_F_1_DOT_6|160|The Aperture value is f/1.6.|
|CAMERA_APERTURE_F_1_DOT_7|170|The Aperture value is f/1.7.|
|CAMERA_APERTURE_F_1_DOT_8|180|The Aperture value is f/1.8.|
|CAMERA_APERTURE_F_2|200|The Aperture value is f/2.|
|CAMERA_APERTURE_F_2_DOT_2|220|The Aperture value is f/2.2.|
|CAMERA_APERTURE_F_2_DOT_4|240|The Aperture value is f/2.4.|
|CAMERA_APERTURE_F_2_DOT_5|250|The Aperture value is f/2.5.|
|CAMERA_APERTURE_F_2_DOT_6|260|The Aperture value is f/2.6.|
|CAMERA_APERTURE_F_2_DOT_8|280|The Aperture value is f/2.8.|
|CAMERA_APERTURE_F_3_DOT_2|320|The Aperture value is f/3.2.|
|CAMERA_APERTURE_F_3_DOT_4|340|The Aperture value is f/3.4.|
|CAMERA_APERTURE_F_3_DOT_5|350|The Aperture value is f/3.5.|
|CAMERA_APERTURE_F_4|400|The Aperture value is f/4.|
|CAMERA_APERTURE_F_4_DOT_5|450|The Aperture value is f/4.5.|
|CAMERA_APERTURE_F_4_DOT_8|480|The Aperture value is f/4.8.|
|CAMERA_APERTURE_F_5|500|The Aperture value is f/5.|
|CAMERA_APERTURE_F_5_DOT_6|560|The Aperture value is f/5.6.|
|CAMERA_APERTURE_F_6_DOT_3|630|The Aperture value is f/6.3.|
|CAMERA_APERTURE_F_6_DOT_8|680|The Aperture value is f/6.8.|
|CAMERA_APERTURE_F_7_DOT_1|710|The Aperture value is f/7.1.|
|CAMERA_APERTURE_F_8|800|The Aperture value is f/8.|
|CAMERA_APERTURE_F_9|900|The Aperture value is f/9.|
|CAMERA_APERTURE_F_9_DOT_6|960|The Aperture value is f/9.6.|
|CAMERA_APERTURE_F_10|1000|The Aperture value is f/10.|
|CAMERA_APERTURE_F_11|1100|The Aperture value is f/11.|
|CAMERA_APERTURE_F_13|1300|The Aperture value is f/13.|
|CAMERA_APERTURE_F_14|1400|The Aperture value is f/14.|
|CAMERA_APERTURE_F_16|1600|The Aperture value is f/16.|
|CAMERA_APERTURE_F_18|1800|The Aperture value is f/18.|
|CAMERA_APERTURE_F_19|1900|The Aperture value is f/19.|
|CAMERA_APERTURE_F_20|2000|The Aperture value is f/20.|
|CAMERA_APERTURE_F_22|2200|The Aperture value is f/22.|
|CAMERA_APERTURE_F_UNKNOWN|255|The Aperture value is Unknown.|
### CameraExposure
 * 相机曝光

|名称|值|描述|
| :--------  | :-----  | :----:  |
|CAMERA_EXPOSURE_COMPENSATION_N_5_0|1|The camera's exposure compensation is -5.0ev.|
|CAMERA_EXPOSURE_COMPENSATION_N_4_7|2|The camera's exposure compensation is -4.7ev.|
|CAMERA_EXPOSURE_COMPENSATION_N_4_3|3|The camera's exposure compensation is -4.3ev.|
|CAMERA_EXPOSURE_COMPENSATION_N_4_0|4|The camera's exposure compensation is -4.0ev.|
|CAMERA_EXPOSURE_COMPENSATION_N_3_7|5|The camera's exposure compensation is -3.7ev.|
|CAMERA_EXPOSURE_COMPENSATION_N_3_3|6|The camera's exposure compensation is -3.3ev.|
|CAMERA_EXPOSURE_COMPENSATION_N_3_0|7|The camera's exposure compensation is -3.0ev.|
|CAMERA_EXPOSURE_COMPENSATION_N_2_7|8|The camera's exposure compensation is -2.7ev.|
|CAMERA_EXPOSURE_COMPENSATION_N_2_3|9|The camera's exposure compensation is -2.3ev.|
|CAMERA_EXPOSURE_COMPENSATION_N_2_0|10|The camera's exposure compensation is -2.0ev.|
|CAMERA_EXPOSURE_COMPENSATION_N_1_7|11|The camera's exposure compensation is -1.7ev.|
|CAMERA_EXPOSURE_COMPENSATION_N_1_3|12|The camera's exposure compensation is -1.3ev.|
|CAMERA_EXPOSURE_COMPENSATION_N_1_0|13|The camera's exposure compensation is -1.0ev.|
|CAMERA_EXPOSURE_COMPENSATION_N_0_7|14|The camera's exposure compensation is -0.7ev.|
|CAMERA_EXPOSURE_COMPENSATION_N_0_3|15|The camera's exposure compensation is -0.3ev.|
|CAMERA_EXPOSURE_COMPENSATION_N_0_0|16|The camera's exposure compensation is 0.0ev.|
|CAMERA_EXPOSURE_COMPENSATION_P_0_3|17|The camera's exposure compensation is +0.3ev.|
|CAMERA_EXPOSURE_COMPENSATION_P_0_7|18|The camera's exposure compensation is +0.7ev.|
|CAMERA_EXPOSURE_COMPENSATION_P_1_0|19|The camera's exposure compensation is +1.0ev.|
|CAMERA_EXPOSURE_COMPENSATION_P_1_3|20|The camera's exposure compensation is +1.3ev.|
|CAMERA_EXPOSURE_COMPENSATION_P_1_7|21|The camera's exposure compensation is +1.7ev.|
|CAMERA_EXPOSURE_COMPENSATION_P_2_0|22|The camera's exposure compensation is +2.0ev.|
|CAMERA_EXPOSURE_COMPENSATION_P_2_3|23|The camera's exposure compensation is +2.3ev.|
|CAMERA_EXPOSURE_COMPENSATION_P_2_7|24|The camera's exposure compensation is +2.7ev.|
|CAMERA_EXPOSURE_COMPENSATION_P_3_0|25|The camera's exposure compensation is +3.0ev.|
|CAMERA_EXPOSURE_COMPENSATION_P_3_3|26|The camera's exposure compensation is +3.3ev.|
|CAMERA_EXPOSURE_COMPENSATION_P_3_7|27|The camera's exposure compensation is +3.7ev.|
|CAMERA_EXPOSURE_COMPENSATION_P_4_0|28|The camera's exposure compensation is +4.0ev.|
|CAMERA_EXPOSURE_COMPENSATION_P_4_3|29|The camera's exposure compensation is +4.3ev.|
|CAMERA_EXPOSURE_COMPENSATION_P_4_7|30|The camera's exposure compensation is +4.7ev.|
|CAMERA_EXPOSURE_COMPENSATION_P_5_0|31|The camera's exposure compensation is +5.0ev.|
|CAMERA_EXPOSURE_COMPENSATION_FIXED|255|The camera's exposure compensation is fixed by the camera.|
### CameraImageStatus
 * 相机拍照模式

|名称|值|描述|
| :--------  | :-----  | :----:  |
|CAMERA_IMAGE_IDLE|0|空闲|
|CAMERA_IMAGE_CAPTURING|2|单拍中|
|CAMERA_IMAGE_INTERVAL_IDLE|3|定时拍照空闲|
|CAMERA_IMAGE_INTERVAL_CAPTURING|4|定时拍照中|
|CAMERA_IMAGE_UNKNOWN|255|状态未知|
### CameraISO
 * 相机ISO

|名称|值|描述|
| :--------  | :-----  | :----:  |
|CAMERA_ISO_AUTO|0|相机ISO-AUTO|
|CAMERA_ISO_100|3|ISO-100|
|CAMERA_ISO_200|4|ISO-200|
|CAMERA_ISO_400|5|ISO-400|
|CAMERA_ISO_800|6|ISO-800|
|CAMERA_ISO_1600|7|ISO-1600|
|CAMERA_ISO_3200|8|ISO-3200|
|CAMERA_ISO_6400|9|ISO-6400|
|CAMERA_ISO_FIXED|255|ISO-UNKNOWN|
### CameraMode
 * 相机模式

|名称|值|描述|
| :--------  | :-----  | :----:  |
|CAMERA_MODE_IMAGE|0|拍照模式|
|CAMERA_MODE_VIDEO|1|录像模式|
|CAMERA_MODE_UNKNOWN|255|模式未知|
### CameraResolutionRatio
 * 相机分辨率

|名称|值|描述|
| :--------  | :-----  | :----:  |
|CAPTURE_RESOLUTION_8000X6000|0|80006000|
|CAPTURE_RESOLUTION_4000X3000|1|40003000|
|CAPTURE_RESOLUTION_UNKNOWN|255|未知|
### CameraShutterSpeed
 * 相机快门速度

|名称|值|描述|
| :--------  | :-----  | :----:  |
|CAMERA_MANAGER_SHUTTER_SPEED_1_8000|0|SHUTTER_SPEED_1/8000|
|CAMERA_MANAGER_SHUTTER_SPEED_1_6400|1|SHUTTER_SPEED_1/6400|
|CAMERA_MANAGER_SHUTTER_SPEED_1_6000|2|SHUTTER_SPEED_1/6000|
|CAMERA_MANAGER_SHUTTER_SPEED_1_5000|3|SHUTTER_SPEED_1/5000|
|CAMERA_MANAGER_SHUTTER_SPEED_1_4000|4|SHUTTER_SPEED_1/4000|
|CAMERA_MANAGER_SHUTTER_SPEED_1_3200|5|SHUTTER_SPEED_1/3200|
|CAMERA_MANAGER_SHUTTER_SPEED_1_3000|6|SHUTTER_SPEED_1/3000|
|CAMERA_MANAGER_SHUTTER_SPEED_1_2500|7|SHUTTER_SPEED_1/2500|
|CAMERA_MANAGER_SHUTTER_SPEED_1_2000|8|SHUTTER_SPEED_1/2000|
|CAMERA_MANAGER_SHUTTER_SPEED_1_1600|9|SHUTTER_SPEED_1/1600|
|CAMERA_MANAGER_SHUTTER_SPEED_1_1500|10|SHUTTER_SPEED_1/1500|
|CAMERA_MANAGER_SHUTTER_SPEED_1_1250|11|SHUTTER_SPEED_1/1250|
|CAMERA_MANAGER_SHUTTER_SPEED_1_1000|12|SHUTTER_SPEED_1/1000|
|CAMERA_MANAGER_SHUTTER_SPEED_1_800|13|SHUTTER_SPEED_1/800|
|CAMERA_MANAGER_SHUTTER_SPEED_1_725|14|SHUTTER_SPEED_1/725|
|CAMERA_MANAGER_SHUTTER_SPEED_1_640|15|SHUTTER_SPEED_1/640|
|CAMERA_MANAGER_SHUTTER_SPEED_1_500|16|SHUTTER_SPEED_1/500|
|CAMERA_MANAGER_SHUTTER_SPEED_1_400|17|SHUTTER_SPEED_1/400|
|CAMERA_MANAGER_SHUTTER_SPEED_1_350|18|SHUTTER_SPEED_1/350|
|CAMERA_MANAGER_SHUTTER_SPEED_1_320|19|SHUTTER_SPEED_1/320|
|CAMERA_MANAGER_SHUTTER_SPEED_1_250|20|SHUTTER_SPEED_1/250|
|CAMERA_MANAGER_SHUTTER_SPEED_1_240|21|SHUTTER_SPEED_1/240|
|CAMERA_MANAGER_SHUTTER_SPEED_1_200|22|SHUTTER_SPEED_1/200|
|CAMERA_MANAGER_SHUTTER_SPEED_1_180|23|SHUTTER_SPEED_1/180|
|CAMERA_MANAGER_SHUTTER_SPEED_1_160|24|SHUTTER_SPEED_1/160|
|CAMERA_MANAGER_SHUTTER_SPEED_1_125|25|SHUTTER_SPEED_1/125|
|CAMERA_MANAGER_SHUTTER_SPEED_1_120|26|SHUTTER_SPEED_1/120|
|CAMERA_MANAGER_SHUTTER_SPEED_1_100|27|SHUTTER_SPEED_1/100|
|CAMERA_MANAGER_SHUTTER_SPEED_1_90|28|SHUTTER_SPEED_1/90|
|CAMERA_MANAGER_SHUTTER_SPEED_1_80|29|SHUTTER_SPEED_1/80|
|CAMERA_MANAGER_SHUTTER_SPEED_1_60|30|SHUTTER_SPEED_1/60|
|CAMERA_MANAGER_SHUTTER_SPEED_1_50|31|SHUTTER_SPEED_1/50|
|CAMERA_MANAGER_SHUTTER_SPEED_1_40|32|SHUTTER_SPEED_1/40|
|CAMERA_MANAGER_SHUTTER_SPEED_1_30|33|SHUTTER_SPEED_1/30|
|CAMERA_MANAGER_SHUTTER_SPEED_1_25|34|SHUTTER_SPEED_1/25|
|CAMERA_MANAGER_SHUTTER_SPEED_1_20|35|SHUTTER_SPEED_1/20|
|CAMERA_MANAGER_SHUTTER_SPEED_1_15|36|SHUTTER_SPEED_1/15|
|CAMERA_MANAGER_SHUTTER_SPEED_1_12DOT5|37|SHUTTER_SPEED_1/12.5|
|CAMERA_MANAGER_SHUTTER_SPEED_1_10|38|SHUTTER_SPEED_1/10|
|CAMERA_MANAGER_SHUTTER_SPEED_1_8|39|SHUTTER_SPEED_1/8|
|CAMERA_MANAGER_SHUTTER_SPEED_1_6DOT25|40|SHUTTER_SPEED_1/6.25|
|CAMERA_MANAGER_SHUTTER_SPEED_1_5|41|SHUTTER_SPEED_1/5|
|CAMERA_MANAGER_SHUTTER_SPEED_1_4|42|SHUTTER_SPEED_1/4|
|CAMERA_MANAGER_SHUTTER_SPEED_1_3|43|SHUTTER_SPEED_1/3|
|CAMERA_MANAGER_SHUTTER_SPEED_1_2DOT5|44|SHUTTER_SPEED_1/2.5|
|CAMERA_MANAGER_SHUTTER_SPEED_1_2|45|SHUTTER_SPEED_0.5|
|CAMERA_MANAGER_SHUTTER_SPEED_1_1DOT67|46|SHUTTER_SPEED_1/1.67|
|CAMERA_MANAGER_SHUTTER_SPEED_1_1DOT25|47|SHUTTER_SPEED_1/1.25|
|CAMERA_MANAGER_SHUTTER_SPEED_1|48|SHUTTER_SPEED_1|
|CAMERA_MANAGER_SHUTTER_SPEED_1DOT3|49|SHUTTER_SPEED_1.3|
|CAMERA_MANAGER_SHUTTER_SPEED_1DOT6|50|SHUTTER_SPEED_1.6|
|CAMERA_MANAGER_SHUTTER_SPEED_2|51|SHUTTER_SPEED_2|
|CAMERA_MANAGER_SHUTTER_SPEED_2DOT5|52|SHUTTER_SPEED_2.5|
|CAMERA_MANAGER_SHUTTER_SPEED_3|53|SHUTTER_SPEED_3|
|CAMERA_MANAGER_SHUTTER_SPEED_3DOT2|54|SHUTTER_SPEED_3.2|
|CAMERA_MANAGER_SHUTTER_SPEED_4|55|SHUTTER_SPEED_4|
|CAMERA_MANAGER_SHUTTER_SPEED_5|56|SHUTTER_SPEED_5|
|CAMERA_MANAGER_SHUTTER_SPEED_6|57|SHUTTER_SPEED_6|
|CAMERA_MANAGER_SHUTTER_SPEED_7|58|SHUTTER_SPEED_7|
|CAMERA_MANAGER_SHUTTER_SPEED_8|59|SHUTTER_SPEED_8|
|CAMERA_MANAGER_SHUTTER_SPEED_9|60|SHUTTER_SPEED_9|
|CAMERA_MANAGER_SHUTTER_SPEED_10|61|SHUTTER_SPEED_10|
|CAMERA_MANAGER_SHUTTER_SPEED_13|62|SHUTTER_SPEED_13|
|CAMERA_MANAGER_SHUTTER_SPEED_15|63|SHUTTER_SPEED_15|
|CAMERA_MANAGER_SHUTTER_SPEED_20|64|SHUTTER_SPEED_20|
|CAMERA_MANAGER_SHUTTER_SPEED_25|65|SHUTTER_SPEED_25|
|CAMERA_MANAGER_SHUTTER_SPEED_30|66|SHUTTER_SPEED_30|
|CAMERA_MANAGER_SHUTTER_SPEED_UNKNOWN|255|SHUTTER_SPEED_UNKNOWN|
### CameraVideoStatus
 * 相机录像状态

|名称|值|描述|
| :--------  | :-----  | :----:  |
|CAMERA_VIDEO_IDLE|0|录像状态空闲|
|CAMERA_VIDEO_CAPTURING|1|录像中|
|CAMERA_VIDEO_UNKNOWN|255|未知状态|
### CameraVideoStreamBitrate
 * 相机视频流码率

|名称|值|描述|
| :--------  | :-----  | :----:  |
|VIDEOSTREAM_BITRATE_UNKNOWN|-1|码率未知|
|VIDEOSTREAM_BITRATE_1Mbps|1|1Mbps|
|VIDEOSTREAM_BITRATE_2Mbps|2|2Mbps|
|VIDEOSTREAM_BITRATE_3Mbps|3|3Mbps|
|VIDEOSTREAM_BITRATE_4Mbps|4|4Mbps|
|VIDEOSTREAM_BITRATE_5Mbps|5|5Mbps|
|VIDEOSTREAM_BITRATE_6Mbps|6|6Mbps|
|VIDEOSTREAM_BITRATE_7Mbps|7|7Mbps|
|VIDEOSTREAM_BITRATE_8Mbps|8|8Mbps|
### CameraVideoStreamResolution
 * 视频流分辨率

|名称|值|描述|
| :--------  | :-----  | :----:  |
|VIDEOSTREAM_RESOLUTION_UNKNOWN|-1|分辨率未知|
|VIDEOSTREAM_RESOLUTION_1080P|0|1080P|
|VIDEOSTREAM_RESOLUTION_720P|1|720P|
|VIDEOSTREAM_RESOLUTION_VGA|2|480P|
### CameraVideoStreamSource
 * 相机视频流类型

|名称|值|描述|
| :--------  | :-----  | :----:  |
|LIVEVIEW_CAMERA_SOURCE_DEFAULT|0|默认类型（未知类型）|
|LIVEVIEW_CAMERA_SOURCE_WIDE|1|广角|
|LIVEVIEW_CAMERA_SOURCE_ZOOM|2|变焦|
|LIVEVIEW_CAMERA_SOURCE_IR|3|红外|
### CameraZoomRatio
 * 相机变焦倍率

|名称|值|描述|
| :--------  | :-----  | :----:  |
|CAMERA_ELECTRON_ZOOM_X1|1|X1|
|CAMERA_ELECTRON_ZOOM_X2|2|X2|
|CAMERA_ELECTRON_ZOOM_X3|3|X3|
|CAMERA_ELECTRON_ZOOM_X4|4|X4|
|CAMERA_ELECTRON_ZOOM_X5|5|X5|
|CAMERA_ELECTRON_ZOOM_UNKNOWN|255|未知|
