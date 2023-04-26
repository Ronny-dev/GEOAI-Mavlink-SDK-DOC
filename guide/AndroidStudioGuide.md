# AndroidStudio配置工程

### 新建一个Android工程

---

新建一个EmptyActivity的应用工程，您可以参考[入门指南](https://developer.android.com/studio/intro?hl=zh-cn)创建一个Android工程

### 1. 通过JitPack集成SDK（推荐）
---
目前SDK已经上传JitPack进行依赖集成，推荐开发者使用JitPack进行集成并使用

1. 添加JitPack repository 至build文件中
```groovy
allprojects {
		repositories {
			...
            maven {
                allowInsecureProtocol = true
                url 'http://maven.ronny.zone:8081/repository/geoai'
            }
			maven { url 'https://jitpack.io' }
		}
	}
```
2. 添加dependency依赖
```groovy
	dependencies {
	        implementation 'com.geoai.mavlink:mavsdk***'
	}
```
3. 在Androidmanifest中添加相关权限申请
```groovy
<!--允许访问网络，必选权限-->
    <uses-permission android:name="android.permission.INTERNET" />
    <!--允许获取精确位置-->
    <uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />
    <!--允许获取粗略位置-->
    <uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION" />
    <!--允许获取设备和运营商信息-->
    <uses-permission android:name="android.permission.READ_PHONE_STATE" />
    <!--允许获取网络状态-->
    <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
    <!--允许获取wifi网络信息-->
    <uses-permission android:name="android.permission.ACCESS_WIFI_STATE" />
    <!--允许获取wifi状态改变-->
    <uses-permission android:name="android.permission.CHANGE_WIFI_STATE" />
    <!--允许写入扩展存储-->
    <uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE" />
    <!--允许读设备等信息-->
    <uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE" />
```

### 2. 通过aar文件集成SDK

---

将下载的aar文件通过拷贝的形式复制到工程，如您使用ArcticFox及以上版本，请参考如下集成方式

1. 依次选择File > Project Structure > Dependencies。
2. 选择要添加库的模块。
3. 在Declared Dependencies标签中，点击+，然后从菜单中选择Module Dependencies。

![Untitled](https://imgs.wiki/imgs/2023/02/27/a5495b453b95a7d1.png)

在Add JAR/AAR Dependency对话框中，选择SDK库模块。

![Untitled](https://imgs.wiki/imgs/2023/02/27/eb731b69ed37053b.png)

选择那个需要此依赖项的配置，或选择 **implementation**（如果库适用于所有配置），然后点击 **OK**。

> Android Studio 会修改模块的 `build.gradle`或 `build.gradle.kts`文件，以便按以下方式添加依赖项
>

```groovy
implementation files('my_path/GEOAI-MAVLINK-SDK.aar')
```

如需导入在 Android Studio 之外运行的 Gradle build 的依赖项，请在应用的 `build.gradle`
或 `build.gradle.kts`文件中添加该依赖项的路径。例如：

```groovy
dependencies {
    implementation fileTree(dir: "libs", include: ["*.jar", "*.aar"])
}
```

> **注意**
：在前面的示例中，**`implementation`**配置将库添加为整个应用模块的 build 依赖项。如需了解如何仅为特定 build 变体配置依赖项，请参阅[配置 build 变体](https://developer.android.com/studio/build/build-variants?hl=zh-cn)。
>

**添加SDK其他依赖源**

目前SDK暂未上传Maven平台，无法进行自动依赖的形式集成，需要用户**自行添加相关依赖库**

1. 添加其他依赖源
```groovy
    //webRTC
    implementation 'org.webrtc:google-webrtc:1.0.32006'
    //MQTT
    implementation 'org.eclipse.paho:org.eclipse.paho.client.mqttv3:1.2.4'
    //ASPECTJ
    implementation 'org.aspectj:aspectjrt:1.9.6'
    //MMKV
    api 'com.tencent:mmkv:1.2.5'
	//GSON
    api 'com.google.code.gson:gson:2.8.5'
    //日志工具
    api 'com.github.xuexiangjys:XLog:1.1.5'
	//rxjava
    api "io.reactivex.rxjava2:rxjava:2.2.20"
    api 'io.reactivex.rxjava2:rxandroid:2.1.0'
```

3. 在Androidmanifest中添加相关权限申请
```groovy
<!--允许访问网络，必选权限-->
    <uses-permission android:name="android.permission.INTERNET" />
    <!--允许获取精确位置-->
    <uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />
    <!--允许获取粗略位置-->
    <uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION" />
    <!--允许获取设备和运营商信息-->
    <uses-permission android:name="android.permission.READ_PHONE_STATE" />
    <!--允许获取网络状态-->
    <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
    <!--允许获取wifi网络信息-->
    <uses-permission android:name="android.permission.ACCESS_WIFI_STATE" />
    <!--允许获取wifi状态改变-->
    <uses-permission android:name="android.permission.CHANGE_WIFI_STATE" />
    <!--允许写入扩展存储-->
    <uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE" />
    <!--允许读设备等信息-->
    <uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE" />
```

3. 添加附加依赖包

   出于功能裁剪考虑，如下两个功能的库固件暂未集成至SDK包中，用户按需集成

- RTSP
- P2P

```groovy
    //rtsp
    compileOnly files('libs/geoai-sdk-rtsp-release_v1.0.aar')
    //zerotier
    compileOnly files('libs/libzt-release.aar')
```

注意：需要在App壳工程中依赖以上库文件，请不要在库工程中依赖。