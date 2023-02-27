# RTK模块指南

RTK（Real-time Kinematic）即载波相位动态实时差分技术，是常用的全球定位测量方法，可提供厘米级的定位精度。

RTK可以准确定位飞行器的实时位置，以便快速、准确地完成航空航海航空航空和UAV飞行。它通过分析来自射线跟踪台的GPS/GLONASS的差异数据，提供精确的实时信息，该信息可用于精确的地理测绘，以及在UAV飞行控制上也可产生巨大的改进。它可以在任何时候为飞行提供精准的纠正信息，确保飞行期间的精准稳定，满足用户要求的航空航空航海航空和UAV飞行控制应用，以及各种类型的数据搜集和时间误差补偿。

> 目前无人机仅支持通过地面站发送RTCM数据至飞行器，详情可以翻阅使用实例。
>

**目前支持的网络RTK形式如下所示，其他形式的差分数据未经测试谨慎使用。**

- 网络RTK：通过地面站与网络基准站进行交互，获取差分数据后发送至无人机
    - 千寻网络RTK
    - 中国移动RTK
    - 南方测绘RTK
    - 南方测绘G13/S10自建站RTK

### SDK框架逻辑

---

图示为完整的SDKManager逻辑流程示例，详细的使用方法请查看文档中的RTK管理类RTKManager.

![RTK模块业务逻辑图.jpg](https://imgs.wiki/imgs/2023/02/27/a6692dc3cd8122d7.jpg)

### SDK流程设计

---

- 用户需要在调用`connectToNtripRTK`前设置Ntrip账密信息，否则无法正常连接RTK服务。
- 用户可以在`setRtkStateListener`获取RTK组件的基础状态，用于判断RTK基础数据回调，常用异步监听接口如下：
    - latitude //飞行器融合返回的纬度
    - longitude //飞行器融合返回的经度
    - isHealth //是否正确解算RTCM数据
    - satelliteCount //参与解算的卫星数
    - accuracy //RTK估算的精度
    - ntripServiceCode //当前Ntrip服务（网络RTK服务）的返回码
    - posType //当前定位解状态
- `setRtkEnable`和`getRtkEnable`表示当前是否传输RTCM数据至飞行器，飞行器中并无**RTK模块开关的概念（飞行器允许GPS模式起飞）**
    - 起飞前固定解——RTK飞行
    - 起飞前单点解——GPS飞行
    - 起飞前固定解，起飞后单点解——起飞前RTK，单点解后GPS飞行
    - 起飞后关闭RTK，一段时间后单点解——关闭后仍以RTK飞行一段时间，单点解后GPS飞行
    - 起飞前单点解，起飞后打开RTK并固定解——GPS起飞，空中RTK飞行
- 用户可以自行调用`sendRTCM` 接口发送差分信号至飞行器，**发送时必须清晰自己在发送什么数据，数据错误可能导致飞行器定位异常**


    ```
    // ---NtripServiceCode ---
    
    CODE_RTK_ERROR_CONNECTED_FAILED= -10210;
    CODE_RTK_ERROR_SERVER_RECEIVED_DATA_FAILED= -10211;
    CODE_RTK_ERROR_SERVER_UNKNOWN_EXCEPTION= -10212;
    CODE_RTK_ERROR_NTRIP_AUTH_FAILED= -10213;
    CODE_RTK_ERROR_UNABLE_RECEIVED_GGA= -10214;
    CODE_RTK_ERROR_UNABLE_RECEIVED_RTCM= -10215;
    CODE_RTK_NOT_CONNECTED= 0;
    CODE_RTK_CONNECTING= 10200;
    CODE_RTK_CONNECTED= 10201;
    ```