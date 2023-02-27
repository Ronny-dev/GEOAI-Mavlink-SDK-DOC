# 入门指南

本指南是向Android应用添加GEOAI-SDK的快速入门指南

### 第一步：下载并安装AndroidStudio

---

按照 Android Studio 编译器安装指南[下载](https://developer.android.com/sdk/index.html)并[安装](http://developer.android.com/sdk/installing/index.html?pkg=studio)Android Studio。（注：下载地址为Google官方网站）

### 第二步：获取SDK接入License

---

> 暂时未开放接入，可跳过此处配置
>

### 第三步：**创建项目**

---

按以下步骤新建一个 Empty Activity 的应用项目。

1. 启动 Android Studio。如果您看到 Welcome to Android Studio 对话框，请选择 Start a new Android Studio project，否则，请点击 Android Studio 菜单栏中的 File，然后点击 New->New Project，按提示输入您的应用名称、公司域和项目位置。 然后点击 Next。
2. 选择您的应用所需的机型。 如果您不能确定自己的需要，只需选择 Phone and Tablet。然后点击 Next。
3. 在“Add an activity to Mobile”对话框中选择 Empty Activity。 然后点击 Next。
4. 按提示输入 Activity 名称、布局名称和标题。 使用默认值即可。 然后点击 Finish。

### 第四步：下载并安装开发包

---

请将获取的开发包解压

解压后，会得到一个aar文件，请您将aar文件添加到工程中，操作步骤请参考[AndroidStudio开发指南](https://developer.android.com/studio/projects/android-library?hl=zh-cn)

### 第五步：Hello SDK

---

1、配置AndroidManifest xml文件

默认情况下，AndroidManifest.xml 位于所设置项目目录main文件下。

在AndroidManifest.xml中配置权限：

```xml
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

<!--允许写设备缓存-->
<uses-permission android:name="android.permission.WRITE_SETTINGS" />  

<!--允许写入扩展存储-->
<uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE" /> 

<!--允许读设备等信息-->
<uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE" />
```

2、Application接入：

```java
public void onCreate() {
    super.onCreate();
    SDKManager.getInstance().setApp(this);//授权SDK获取Application
}
```

3、应用层接入：

```java
//传入应用上下文，日志存储路径
StarLinkClientManager.getInstance().register(getBaseContext(), GCS_LOG_PATH);
//启动连接
StarLinkClientManager.getInstance().openConnection();
```

当有符合协议版本的无人机设备接入后，SDK会通过异步回调的形式返回连接对象。

```java
StarLinkClientManager.getInstance().setProductConnectionListener(new IProductsConnectionListener())
```

用户也可以主动获取当前连接的对象。

```java
StarLinkClientManager.getInstance().getProductManager()
```

### 第六步：**后续步骤**

您可以前往开发指南，阅读更多相关内容。