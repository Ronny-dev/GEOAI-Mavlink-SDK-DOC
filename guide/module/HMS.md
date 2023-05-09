# 健康管理系统

### 名词解析

HMS： HealthyManagerSystem（健康管理系统）

EventReport：事件上报

### 如何使用

当飞行器或者飞行器相关的其他组件需要上报事件时，将会**主动发送该信号指令到地面站系统中**。用户可以调用相关的接口API获取上报的事件类型和事件码，通过解析事件描述文件内容来判断该事件的名称和消息。

目前用户可以通过飞控组件设置HMS监听器：

```java
flyControllerManager.setDiagnosticsStateListener(new IDiagnosticsStateListener() {
        @Override
        public void onDiagnosticsStateListener(List<AircraftDiagnosticsStateInfo> info) {
            // List<AircraftDiagnosticsStateInfo>
        }
    });
```

在驱动层，MavSDK已经做好EventReport，并且1s一次通知应用层开发者当前系统存在的事件。

在AircraftDiagnosticsStateInfo中将信息分成如下几个等级：

- *`EMERGENCY`*
- *`ALERT`*
- *`CRITICAL`*
- *`ERROR`*
- *`WARNING`*
- *`NOTICE`*
- *`INFO`*
- *`DEBUG`*

开发者可以根据事件类型来绘制不同的界面提供给使用者进行区分事件严重程度。

### 示例程序

用户可以下载[GCS程序源码](https://github.com/Ronny-dev/GCS)进行学习使用，其中HMS使用入口位置在下图红框位置：

![Untitled](https://imgs.wiki/imgs/2023/05/09/4ebc7b89bc485a86.png)

### 需要注意

在AircraftDiagnosticsStateInfo中的字段[HoldTime]表明该消息的持续时间

- =0: 触发类事件
- >0: 状态类事件

用户可以根据这个字段提供事件信息的相关UI控制。

### 事件描述文件示例

```json
{
    "version": 1, //版本号
    "components": {
        "1": { //组件ID
            "namespace": "px4",
            "event_groups": {
                "default": {
                    "events": {
                        "2159698": { //事件ID
                            "name": "commander_high_wind_warning", //事件名称
                            "message": "High wind speed detected ({1:.1m/s}), landing advised", //消息
                            "arguments": [ //消息参数
                                {
                                    "type": "float",
                                    "name": "arg0"
                                }
                            ]
                        },
                        "12894058": {
                            "name": "sensor_failover",
                            "message": "{1} sensor #{2} failure",
                            "description": "Land immediately and check the system.",
                            "arguments": [
                                {
                                    "type": "px4::sensor_type_t",
                                    "name": "arg0"
                                },
                                {
                                    "type": "uint8_t",
                                    "name": "arg1"
                                }
                            ]
                        },
                    }
                }
            }
            "enums": {
                "sensor_type_t": {
                    "type": "uint8_t",
                    "description": "Sensor type for failover reporting",
                    "entries": {
                        "0": {
                            "name": "accel",
                            "description": "Accelerometer"
                        },
                        "1": {
                            "name": "gyro",
                            "description": "Gyroscope"
                        },
                        "2": {
                            "name": "mag",
                            "description": "Magnetometer"
                        }
                    }
                }
            }
        }
    }
}
```

### 相关资料

事件码匹配文件：[https://github.com/zouyulongzone/MAVLink/blob/main/通用消息/json/all_events.json](https://github.com/zouyulongzone/MAVLink/blob/main/%E9%80%9A%E7%94%A8%E6%B6%88%E6%81%AF/json/all_events.json)

事件播报协议：[https://github.com/zouyulongzone/MAVLink/blob/main/子协议/事件播报协议.md](https://github.com/zouyulongzone/MAVLink/blob/main/%E5%AD%90%E5%8D%8F%E8%AE%AE/%E4%BA%8B%E4%BB%B6%E6%92%AD%E6%8A%A5%E5%8D%8F%E8%AE%AE.md)