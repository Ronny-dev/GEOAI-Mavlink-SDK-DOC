# 参数配置指南

### 写在前面

---

飞行器提供了统一配置的入口，用于设置飞行器的相关配置。在一般情况下，用户不需要研究此项内容，如果错误修改配置的信息，有可能会导致飞行器处于异常工作的状态。

- 飞控系统设置
- ESC设置
- 控制量设置
- 飞行功能设置

在SDK中，已经将常用的接口进行提取并封装，用户不需要单独进行更深纬度的配置。如果用户需要，可以在`SystemManager`保留的接口中进行相关的配置读取和设置

1. `readAllParameter` 读取所有参数名和参数值
2. `readSingleParameter` 读取单个参数值
3. `writeSingleParameter` 写入单个参数值

### SDK内部参数配置流程图

---

![SDK内部参数配置流程图.jpg](https://imgs.wiki/imgs/2023/02/27/571656f694694318.jpg)

### 配置文件保存路径

---

Drone: /etc/extras/parameters.json.xz

SDK: /storage/sdcard0/Android/data/[package]/files/parameters.json

### SDK内部使用参数配置接口

---

SDK内部有部分接口需要使用[参数配置]进行实现，SDK已经完成了接口的封装与暴露，用户可以直接调用相关接口进行配置，无需关心配置底层的实现过程与原理。

- 电池低电量提醒阈值
- 电池低电量智能返航阈值
- 电池低电量迫降阈值
- 飞控是否允许无GPS起飞
- 飞控俯仰\横滚最大速度
- 飞控油门最大速度
- 飞控视觉降落超时设定
- 飞控视觉降落搜索目标高度设定
- 飞控返航高度
- 飞控返航模式

### SampleDemo

---

用户可以访问GCS的示例代码，在MainActivity中已经实现了一套仿照QGC UI设计的参数配置页面，其中包含了参数的获取和配置功能。
[GCS](https://github.com/Ronny-dev/GCS)

### 协议实现

---

[PX4自驾仪参数设置](https://docs.px4.io/main/zh/advanced/parameters_and_configurations.html)

[MAV Parameter Protocol](https://mavlink.io/en/services/parameter.html)

Parameter.json中文参考