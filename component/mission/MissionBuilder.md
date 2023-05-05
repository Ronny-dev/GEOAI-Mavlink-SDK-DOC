# 任务相关接口文档

## Builder

|  | 名称 | 描述 |
| --- | --- | --- |
| 方法名 | setHeadingMode | 设置任务朝向模式 |
| 参数类型 | MissionFinishAction | 枚举值 |
| 参数 | MISSION_FINISH_ACTION_NO_ACTION = 250 | 无动作 |
|  | MISSION_FINISH_ACTION_GO_HOME = 5 | 返航 |
|  | MISSION_FINISH_ACTION_AUTO_LAND = 6 | 原地降落 |
|  | MISSION_FINISH_ACTION_GO_RALLY = 7 | 前往备降点 |

|  | 名称 | 描述 |
| --- | --- | --- |
| 方法名 | setFinishAction | 设置任务结束动作 |
| 参数类型 | MissionHeadingMode | 枚举值 |
| 参数 | MISSION_HEADING_MODE_AUTO = 1 | 自动朝向模式 |
|  | MISSION_HEADING_MODE_WAYPOINT = 3 | 使用航点朝向 |

|  | 名称 | 描述 |
| --- | --- | --- |
| 方法名 | setMissionSpeed | 设置航线缺省速度 |
| 参数类型 | speed | 浮点值 |

<aside>
💡 此处的速度为缺省配置，如果所有的waypoint中均设置了航点速度，则此速度不会生效

</aside>

|  | 名称 | 描述 |
| --- | --- | --- |
| 方法名 | setWaypointList | 设置航点列表 |
| 参数类型 | List<Waypoint> | 列表 |

<aside>
💡 通过此接口设置Waypoint细节，具体看Waypoint实例文档
</aside>

## Waypoint

|  | 名称 | 描述 |
| --- | --- | --- |
| 方法名 | setWayPointLatitude | 设置航点纬度 |
| 参数类型 | latitude | 浮点值 |

|  | 名称 | 描述 |
| --- | --- | --- |
| 方法名 | setWayPointLongitude | 设置航点经度 |
| 参数类型 | longitude | 浮点值 |

|  | 名称 | 描述 |
| --- | --- | --- |
| 方法名 | setWayPointAltitude | 设置航点高度 |
| 参数类型 | altitude （AGL） | 浮点值 |

<aside>
💡 此处为Above Ground Level高度，如果需要MSL，需要用户在起飞前自行设定

</aside>

|  | 名称 | 描述 |
| --- | --- | --- |
| 方法名 | setWayPointSpeed | 设置航点速度 |
| 参数类型 | speed (m/s) | 浮点值 |

|  | 名称 | 描述 |
| --- | --- | --- |
| 方法名 | setShootPhotoTimeInterval | 设置航点定时拍照属性 |
| 参数类型 | shootPhotoTimeInterval (s) | 浮点值 |

|  | 名称 | 描述 |
| --- | --- | --- |
| 方法名 | setShootPhotoDistanceInterval | 设置航点定距拍照属性 |
| 参数类型 | shootPhotoDistanceInterval (cm) | 浮点值 |

|  | 名称 | 描述 |
| --- | --- | --- |
| 方法名 | setActions | 设置航点动作 |
| 参数类型 | ActionParam[] | Action数组 |

<aside>
💡 通过此接口配置航点动作，具体查阅ActionParam实例文档

</aside>


## ActionParam

| 参数名 | 参数单位 |
| --- | --- |
| ACTION_AIRCRAFT_STAY | s |
| ACTION_AIRCRAFT_ROTATE | deg（-pi ~ +pi） |
| ACTION_TAKE_PHOTO | - |
| ACTION_START_RECORD | - |
| ACTION_STOP_RECORD | - |
| ACTION_CAMERA_ZOOM_RATIO | ratio（0-100） |
| ACTION_CAMERA_ZOOM_FOCAL | focal（focal lens） |
| ACTION_GIMBAL_YAW | deg（-pi ~ +pi） |
| ACTION_GIMBAL_PITCH | deg（30~-90） |