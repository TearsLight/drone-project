## 项目结构如下
drone-project/
├── core/                           # C++核心模块
│   ├── include/                    # 头文件
│   │   ├── drone_types.h           # 共享数据结构
│   │   └── comm.h                  # 通信接口声明
│   ├── src/
│   │   ├── control/                # 控制算法
│   │   │   ├── pid.cpp             # PID控制器
│   │   │   └── estimator.cpp       # 姿态解算
│   │   ├── drivers/                # 硬件驱动
│   │   │   ├── imu.cpp             # IMU传感器驱动
│   │   │   └── motor.cpp           # 电机控制
│   │   ├── comm/                   # 通信实现
│   │   │   ├── shm_handler.cpp     # 共享内存操作
│   │   │   └── socket_server.cpp   # TCP服务端
│   │   └── main.cpp                # C++主程序
│   ├── CMakeLists.txt              # 编译配置
│   └── lib/                        # 依赖库
├── python/                         # Python辅助模块
│   ├── vision/                     # 视觉处理
│   │   ├── detector.py             # 目标检测
│   │   └── socket_client.py        # 向C++发送视觉结果
│   ├── comm/                       # 通信客户端
│   │   ├── mavlink_ground.py       # 地面站MAVLink通信
│   │   └── shm_reader.py           # 从共享内存读姿态数据
│   ├── utils/
│   │   ├── logger.py               # 日志记录
│   │   └── calibrate.py            # 传感器校准
│   └── main.py                     # Python主程序
├── java/                           # Java模块
│   ├── src/main/java/com/drone/
│   │   ├── server/                 # HTTP服务
│   │   │   └── DroneServer.java    # 接收远程控制指令
│   │   ├── comm/
│   │   │   └── TcpClient.java      # 向C++发送指令
│   │   └── Main.java               # Java主程序
│   ├── pom.xml                     # Maven依赖
├── comm_proto/                     # 公共通信协议
│   ├── msg.proto                   # Protocol Buffers定义
│   └── json_schema/                # JSON数据结构模板
├── config/                         # 全局配置
│   ├── params.yaml                 # 飞行参数
│   └── ipc_config.json             # 通信配置
├── scripts/                        # 部署脚本
│   ├── start_all.sh                # 启动所有模块
│   └── build_core.sh               # 编译C++核心程序
└── README.md                       # 多语言协作说明
## 项目材料
| 组件类别        | 产品型号规格                           | 数量 | 单价          |
| ----------- | -------------------------------- | -- | ----------- |
| 主处理器        | Raspberry Pi 4B 8GB              | 1  | -           |
| 飞行控制单元      | Arduino Uno R3                   | 1  | -           |
| 惯性测量单元（IMU） | MPU-9250                         | 1  | ¥53.00      |
| 无刷电调        | XXD 30A XT                       | 1  | ¥23.40      |
| 2.4G 通信模块   | Wemos CH340 NODEMCU              | 1  | ¥11.96      |
| 供电模块        | 锂聚合电池 3S-4200mAh-75C             | 1  | ¥102.60     |
| 降压模块        | BEC 降压模块 5V 5A                   | 1  | ¥19.00      |
| GPS 定位模块    | NEO-6M 天线                        | 1  | ¥14.00      |
| 气压湿度测量模块    | BME-280-5V                       | 1  | ¥13.80      |
| 无刷电机（含螺旋桨）  | A2208 1400KV + 螺旋桨               | 4  | ¥161.60     |
| 摄像头         | 树莓派 Camera Module V2 1080P 30FPS | 1  | ¥133.65     |
| 连接配件        | 杜邦线（公对母 / 公对公 / 母对母）120 根        | 1  | ¥7.44       |
| **合计**      | -                                | -  | **¥540.45** |
