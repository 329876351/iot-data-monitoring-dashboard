工业物联网设备数据采集与实时监控看板

项目背景
本项目针对工业自动化场景中传感器数据的低延迟采集与实时可视化需求，基于 Node.js 与 WebSocket 协议搭建了一套轻量级 IoT 数据监控看板系统。系统实时模拟现场工业设备（如温度传感器、压力变送器）的连续数据采集，并以毫秒级响应同步渲染至前端 Web 界面。

核心功能
1. 实时数据推送
基于 WebSocket 全双工通信，实现服务端至客户端 1000ms 频率的高频数据实时传输。

2. 可视化图表看板
前端基于 Chart.js 实现响应式渲染，实时更新双通道（温度/压力）平滑折线图，支持历史数据自动滑动清理。

3. 连接状态感知
前端实时感知 WebSocket 链路状态（已连接/连接断开），提供直观的状态提示。

4. 模块化设计
服务端托管与数据生成解耦，架构设计便于后续扩展真实硬件通信协议（如 Modbus RTU/TCP、MQTT）。

技术选型
| 模块 | 技术选型 | 说明 |
| :--- | :--- | :--- |
| **后端 (Backend)** | Node.js / Express | Web 服务与静态资源托管 |
| **通信协议** | WebSocket (ws) | 全双工实时数据传输 |
| **前端 (Frontend)** | HTML5 / CSS3 / ES6 JS | 前端界面与交互逻辑 |
| **数据可视化** | Chart.js | 动态折线图渲染 |
| **版本控制** | Git / GitHub | 代码版本管理 |

项目目录结构
```text
iot-data-monitoring-dashboard/
├── public/
│   └── index.html       # 前端监控看板主页面（含 Chart.js 与 WS 逻辑）
├── .gitignore           # Git 忽略文件配置
├── package.json         # 项目配置文件与依赖管理
├── README.md            # 项目说明文档
└── server.js            # Node.js 服务端主入口（含有 WebSocket 服务）
快速启动

安装依赖：

Bash
npm install
启动服务：

Bash
node server.js
访问应用：
打开浏览器访问 http://localhost:3000

API 与通信协议说明

WebSocket 通信

接口地址：ws://localhost:3000

传输频率：1000ms

数据格式示例：

JSON
{
  "timestamp": "14:20:05",
  "temperature": 45.2,
  "pressure": 1.02
}
