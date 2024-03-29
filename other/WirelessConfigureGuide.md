# 无线电模块配置文档

| 日期 | 描述 | 作者 |
| --- | --- | --- |
| 2023年3月28日 | 文档创建 | Ronny |
| 2023年3月30日 | 增加安卓配置 | Ronny |

自研无人机天空端和地面端均使用宸芯无线电模块进行通讯（2023-03-28），在出厂前需要对无线电模块进行相关的参数配置。研发团队制作了程序简化配置的过程，具体配置过程参考以下配置说明文档。

目前可以使用配置程序进行安卓的IP配置，具体配置过程参考以下配置说明文档。

### 设备准备

1. 无线电模块（6602N）
2. pc电脑（windows带python环境）
3. microUSB线缆
4. 无线电模块供电线

### 环境准备

1. python3 环境
2. 无线电模块驱动程序
3. pyserial库程序
4. 配置脚本

### 接线示意

![接线示意](https://imgs.wiki/imgs/2023/03/28/d43bcd047ace294a.png)

<aside>
💡 无线电模块上电前确保天线正确连接，**避免射频模块损坏。**

</aside>

### 写在前面

在0330后提供的配置程序中，可以进行安卓工控板eth1的网卡IP设置。在整个网络拓扑中必须按照设计进行配置，否则会导致应用相关功能无法实现。

在整个网络中的拓扑如下所示：

![网络拓扑示意](https://imgs.wiki/imgs/2023/03/30/f67d955444597e34.png)

1. 机载电脑：上电后通过USB读取配置IP
2. 天空端：使用程序配置
3. 地面端：使用程序配置
4. 安卓工控机：使用程序配置

### 环境变量配置/IP配置

1. 根据[文档](https://blog.csdn.net/qq_59636442/article/details/123079968)配置pc的python环境变量（若已经安装python环境则忽略）
    1. 可以通过cmd输入[python]查看环境是否正确配置

   ![python环境配置](https://imgs.wiki/imgs/2023/03/28/02d21f1e8eb588ae.png)

2. 安装pyserial库
    1. 如果安装2.*版本的python则安装命令：[pip install pyserial]
    2. 如果安装3.*版本的python则安装命令：[pip3 install pyserial]
3. 安装无线电模块驱动程序
    1. 请联系研发人员获取驱动安装程序
    2. 安装程序[UsbVcom]
4. 运行程序
    1. 请联系研发人员获取无线电配置程序
    2. 运行命令：[python wireless_configure.py]
    3. 运行程序后提示节点类型，请按需选择

   ![运行程序](https://imgs.wiki/imgs/2023/03/28/0f9d385bb17d1ff5.png)

5. 断开电源，重新上电。至此全部配置完毕。

### 注意

- 在进行安卓IP配置前，**需要连接地面站无线电模块进行配置**，否则无法记录SN值
- 在进行安卓IP配置前，需要按提示**移除无线电模块USB线缆，**否则配置失败
- 配置完毕后，可以使用SDK程序或Sample检查无线电是否正常连接

### 常见问题

1. 提示[未发现无线电串口设备，请确保驱动已安装]
    1. 请确保驱动正确安装，在windows设备管理器中能正确找到设备

![端口连接状态](https://imgs.wiki/imgs/2023/03/28/4eba0ef68436ecb5.png)

1. 提示[请按规则输入设备类型.]
    1. 请确保输入正确：1：中心节点；2：接入节点；3：安卓板配置