# 工业物联网（IoT）设备数据采集与实时监控看板

![Node.js](https://img.shields.io/badge/Node.js-v18+-green.svg)
![Express](https://img.shields.io/badge/Express-4.x-blue.svg)
![WebSocket](https://img.shields.io/badge/WebSocket-ws-orange.svg)
![License](https://img.shields.io/badge/license-MIT-brightgreen.svg)

## 📌 项目背景
本项目针对工业自动化场景中传感器数据的低延迟采集与实时可视化需求，基于 **Node.js** 与 **WebSocket** 协议搭建了一套轻量级的 IoT 数据监控看板系统。该系统能够模拟现场工业设备（如温度传感器、压力变送器、电机转速）的连续数据采集，并以毫秒级响应实时渲染至前端 Web 界面。

---

## ✨ 核心功能
- **实时数据推送：** 基于 WebSocket 双向通信，实现服务器与客户端之间 1000ms 频率的高频实时数据传输。
- **可视化图表看板：** 前端基于 Chart.js 响应式渲染，实时更新双通道（温度/压力）平滑折线图，支持历史数据自动滑动清理。
- **连接状态感知：** 前端感知 WebSocket 链路状态（已连接/连接断开），实现可视化的状态提醒。
- **模块化设计：** 服务端托管与数据生成解耦，便于后续扩展真实硬件通信协议（如 Modbus RTU/TCP、MQTT）。

---

## 🛠️ 技术栈

| 模块 | 技术 / 库 | 说明 |
| :--- | :--- | :--- |
| **后端 (Backend)** | Node.js, Express | Web 服务器与静态资源托管 |
| **通信协议 (Protocol)** | WebSocket (`ws` 库) | 全双工实时数据传输 |
| **前端 (Frontend)** | HTML5, CSS3, ES6 JavaScript | 前端界面与交互逻辑 |
| **数据可视化 (Chart)** | Chart.js | 动态折线图渲染 |
| **版本控制 (VCS)** | Git & GitHub | 代码版本管理与协作 |

---

##  项目目录结构

```text
iot-data-monitoring-dashboard/
├── node_modules/         # 第三方依赖包
├── public/               # 前端静态资源目录
│   └── index.html        # 前端监控看板主页面 (含 Chart.js 与 WS 逻辑)
├── .gitignore            # Git 忽略文件配置
├── package.json          # 项目配置文件与依赖管理
├── package-lock.json     # 依赖版本锁定文件
├── README.md             # 项目说明文档
└── server.js             # Node.js 服务端主入口文件