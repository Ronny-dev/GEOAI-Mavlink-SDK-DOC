# 航线任务使用教程

当今无人机技术的快速发展，越来越多的应用场景需要无人机实现自主化飞行。而无人机的自主化飞行往往需要实现航点飞行功能。

Mavlink协议是一种轻量级的通信协议，被广泛应用于无人机的通信控制中。使用Mavlink实现航点飞行功能，可以实现无人机在事先设定好的航点上自主飞行。在本文档中，我们将介绍如何使用MavSDK实现无人机航点飞行功能，包括航点的设置、动作指令的发送等关键步骤。通过学习本文档，读者将能够了解如何使用MavSDK实现无人机的自主化飞行，并在实际应用中应用此技术。

---

### 技术路线

在MavSDK中与飞行器的任务交互如下图所示，开发者如果对Mission协议感兴趣可访问[Mavlink协议官网](https://mavlink.io/en/services/mission.html)进行学习。

![Untitled](https://imgs.wiki/imgs/2023/05/05/c5473ea6f112aa28.png)

> 目前仅完整支持云冠v1.2或以上版本，自研飞控仅支持部分设计（后续完善）。
>

MavSDK提供的航线功能结构较为简单，调用流程如下图所示。详细的使用接口请查看MavSDK API文档中航线任务相关的管理类[MissionManager](https://ronny-dev.github.io/GEOAI-Mavlink-SDK-DOC/#/component/mission/all)。

![Untitled](https://imgs.wiki/imgs/2023/05/05/8ea7b0b2afd84fd3.png)

### 实例化MissionBuilder

在架构设计中，MissionItemBuilder以单例的形式暴露给开发者，开发者可以在与无人机建立正常通讯后，通过实例化MissionItemBuilder的方式获取任务构建器。关于任务构建器相关的接口使用方式可以参考[任务构建器](https://ronny-dev.github.io/GEOAI-Mavlink-SDK-DOC/#/component/mission/MissionBuilder)进行查阅。

```java
MissionItemBuilder.Builder builder = new MissionItemBuilder.Builder();
```

### 配置航线属性

在builder的最外层，用户可以配置任务航线的属性，比如航线速度，航线完成方式等。在builder的设置中还需要传入Waypoint（航点）列表，稍后在下个章节中体现。

P.S可以使用构造器模式传入相关参数

```java
MissionItemBuilder builder = new MissionItemBuilder.Builder()
           .setMissionSpeed(8.0f)
           .setFinishAction(MissionItemBuilder.MissionFinishAction.MISSION_FINISH_ACTION_GO_HOME)
           .setHeadingMode(MissionItemBuilder.MissionHeadingMode.MISSION_HEADING_MODE_AUTO)
           .setWaypointList(...) //todo WaypointList
           .build();
```

### 配置航点属性

在上个章节的示例中需要传入的航点列表参数，在设计中是**数据实例**，用户需要手动创建waypoint列表并针对每个waypoint进行赋值和设定参数。内部变量的单位设定请前往[接口文档](https://ronny-dev.github.io/GEOAI-Mavlink-SDK-DOC/#/component/mission/MissionBuilder?id=waypoint)查阅。

> **在任务执行的过程中，飞行器会根据列表的放置顺序进行航点任务的执行。**
>

```java
// init waypoint list
List<MissionItemBuilder.Waypoint> waypointList = new ArrayList<>();
// looper configure waypoint parameter
for (int i = 0; i < 3; i++) {
    MissionItemBuilder.Waypoint waypoint = new MissionItemBuilder.Waypoint();
    waypoint.setWayPointLatitude(23.0d);
    waypoint.setWayPointLongitude(113.0d);
    waypoint.setWayPointAltitude(10.0f);
    waypoint.setActions(...); //todo wyapoint actions
    waypointList.add(waypoint);
}
// set mission builder
missionItemBuilder.setWaypointList(waypointList);
```

### 配置航点动作

在上个章节的示例中需要传入航点动作参数，在设计中是**动作数组，**用户需要手动创建actions的数组并针对需要执行的action进行赋值和设定参数。内部变量的action name和action param请前往[接口文档](https://ronny-dev.github.io/GEOAI-Mavlink-SDK-DOC/#/component/mission/MissionBuilder?id=actionparam)查阅。

> **在任务执行的过程中，飞行器到达该航点就会进行动作的顺序执行。**
>

```java
MissionItemBuilder.ActionParam[] actionParams = new MissionItemBuilder.ActionParam[3];
actionParams[0] = new MissionItemBuilder.ActionParam(MissionItemBuilder.ActionParam.ACTION_AIRCRAFT_STAY, "1");
actionParams[1] = new MissionItemBuilder.ActionParam(MissionItemBuilder.ActionParam.ACTION_GIMBAL_PITCH, "-30");
actionParams[2] = new MissionItemBuilder.ActionParam(MissionItemBuilder.ActionParam.ACTION_TAKE_PHOTO, "1");
waypoint.setActions(actionParams);
```

### 任务上传

用户在使用MissionItemBuilder完成了任务的构建后，可以进行任务上传给无人机的动作。

[MissionUploadState](https://ronny-dev.github.io/GEOAI-Mavlink-SDK-DOC/#/component/mission/all?id=missionuploadstate)

```java
// mission upload
missionManager.uploadMission(builder, new IMissionUploadListener() {
    @Override
    public void onMissionUploadState(MissionUploadState state) {
				// mission upload state result
    }

    @Override
    public void onUploadProgress(int index, int progress) {
				// index: current upload seq
				// progress: percentage upload progress
    }

    @Override
    public void onMissionUploadResult(boolean isSuccess, GEOAIError error) {
				// mission upload result
    }
});
```

### 任务启动

用户在使用MissionUpload接口成功上传任务后（MissionUploadState为READY_TO_EXECUTE）并且MissionUploadResult提示上传成功；用户可以使用MissionStart接口进行任务启动。

> **在调用任务启动前必须确保当前无人机环境允许任务启动，并确保航线设定符合预期。**
>

```java
missionManager.startMission(new CompletionCallback.ICompletionCallback() {});
```