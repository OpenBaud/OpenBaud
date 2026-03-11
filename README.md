📡 openbaud

The AI-Powered Protocol Cognitive Engine for IoT.
Translating chaotic, raw IoT telemetry into meaningful digital semantics for humans and AI agents.

<details>
<summary><strong>🇨🇳 点击展开中文版说明 (Click to expand Chinese version)</strong></summary>

💡 什么是 openbaud？

在工业物联网（IIoT）和边缘计算领域，设备碎片化是一个永恒的痛点。面对各种异构的边缘网关、数据采集（DAQ）仪器或是底层传感器，开发者通常需要耗费大量精力去查阅通信手册、编写正则表达式或是手敲硬编码，才能勉强解析出 16 进制的原始报文。

openbaud 致力于彻底打破这个协议黑盒。它不仅是一个高性能的报文解析引擎，更是一个内置了 AI 认知能力的翻译官。

通过集成自研训练的特征识别模型，openbaud 能够直接“阅读”设备上传的原始字节流，自动识别协议特征、动态生成解析规则，并最终输出带有明确业务意义的结构化数值。无论是云端业务平台、人机交互界面（HMI），还是大语言模型驱动的 AI Agents，都可以直接调用这些干净的数据。

✨ 核心特性

🧠 AI 驱动的协议认知 (Cognitive Parsing): 告别繁琐的手动规则配置。内置自训练模型，能够对未知的原始报文进行特征提取与模式识别。

⚙️ 高性能解析引擎 (Dynamic Engine): 接收模型动态输出的解析规则，以极低的延迟将 Hex/Binary 字节流转化为有意义的数值。

🤖 Agent-Ready 架构: 输出标准化的 JSON 格式及带有语义标签的数据，完美无缝对接各类 AI 智能体（Agents）和自动化工作流。

🔌 开箱即用的底层穿透力: 统一复杂的底层数据，轻松应对多样化的物联网通信协议和设备形态。

🎯 典型应用场景

工业 PLC 与控制器接入： 自动破译主流或非标 PLC 的底层通信报文。

电子测量与 DAQ 仪器： 快速解析基于 SCPI 等协议的复杂仪器返回的原始测量数据流。

低功耗广域网（LPWAN）解析： 针对 LoRaWAN 网关上传的加密或压缩 payload 进行智能解包与特征提取。

边缘计算节点： 部署在轻量级边缘网关中，在数据上云前完成“报文 -> 有意义数值”的本地清洗与翻译。

🛠️ 工作原理
```text
[边缘网关 / DAQ 仪器 / PLC / 传感器] 
       | (Raw Hex / Bytes / 原始报文)
       v
+---------------------------------------------------+
|                     openbaud                      |
|                                                   |
|  1. AI Model: 识别报文特征 -> 提取并动态生成解析规则 |
|  2. Engine:   应用规则 -> 执行底层字节到数据的转换   |
+---------------------------------------------------+
       | (Meaningful Values / 结构化 JSON)
       v
[物联网中台 / AI Agents / 数据可视化面板]
```

🚧 当前状态：积极开发中 (Work in Progress)

注意：openbaud 目前正处于密集的早期开发阶段。 架构和 API 可能会随时发生破坏性变更（Breaking changes），暂不建议将其部署到生产环境中。欢迎点击右上角的 Star ⭐️ 关注本项目，见证协议认知引擎的演进！

🗺️ 开发路线图 (Roadmap)

[x] 概念验证 (PoC): 核心模型思路验证与引擎基础架构设计。

[ ] Phase 1: 引擎底座: 构建底层字节流处理模块与规则抽象语法树 (AST)。

[ ] Phase 2: 模型接入: 完成自训练 AI 模型与解析引擎的无缝集成。

[ ] Phase 3: 标准化 API: 提供 HTTP / MQTT / WebSocket 等多协议数据输出接口。

[ ] Phase 4: 开发者 CLI: 发布供开发者在本地测试报文解析的命令行工具。

[ ] Phase 5: Alpha Release: 发布首个可用版本，支持主流工业网关设备的开箱即用。

</details>

💡 What is openbaud?

In the realm of Industrial IoT (IIoT) and edge computing, device fragmentation is a persistent pain point. When dealing with diverse edge gateways, DAQ instruments, or low-level sensors, developers often spend countless hours reading manuals, writing regex, or hardcoding parsers just to make sense of raw hexadecimal payloads.

openbaud is built to shatter this protocol black box. It is not just a high-performance parsing engine; it is an AI-native translator for device communications.

By integrating a custom-trained feature recognition model, openbaud can natively "read" raw byte streams uploaded by devices. It automatically identifies protocol signatures, dynamically generates parsing rules, and outputs structured, business-ready values. Whether it's a cloud platform, an HMI dashboard, or an LLM-driven AI Agent, downstream systems can consume this clean data instantly.

✨ Core Features

🧠 AI-Driven Cognitive Parsing: Say goodbye to tedious manual rule configurations. The built-in trained model extracts features and recognizes patterns from unknown raw payloads.

⚙️ High-Performance Dynamic Engine: Takes dynamically generated rules from the model and translates Hex/Binary byte streams into meaningful values with ultra-low latency.

🤖 Agent-Ready Architecture: Outputs standardized JSON and semantically labeled data, seamlessly integrating with AI Agents and automated workflows.

🔌 Universal Interoperability: Unifies complex low-layer data, easily handling diverse IoT communication protocols and physical device types.

🎯 Typical Use Cases

Industrial PLCs & Controllers: Automatically decode underlying communication packets from mainstream or non-standard PLCs.

Electronic Measurement & DAQ: Rapidly parse raw measurement data streams from complex instruments based on SCPI protocols.

LPWAN & Sensor Networks: Smart unpacking and feature extraction for encrypted or compressed payloads from LoRaWAN gateways.

Edge Computing Nodes: Deploy in lightweight edge gateways to perform local "payload-to-value" cleansing and translation before cloud ingestion.

🛠️ How it Works
```text
[Edge Gateways / DAQ / PLCs / Sensors] 
       | (Raw Hex / Bytes / Payloads)
       v
+---------------------------------------------------+
|                     openbaud                      |
|                                                   |
|  1. AI Model: Identify features -> Generate rules |
|  2. Engine:   Apply rules -> Translate byte stream|
+---------------------------------------------------+
       | (Meaningful Values / Structured JSON)
       v
[IoT Platforms / AI Agents / Dashboards]
```

🚧 Status: Work in Progress

Note: openbaud is currently in heavy, early-stage development. The architecture and APIs are subject to breaking changes at any time. It is not yet recommended for production environments. However, we highly encourage you to hit the Star ⭐️ button to follow the project!

🗺️ Roadmap

[x] Proof of Concept (PoC): Core model validation and engine architecture design.

[ ] Phase 1: Engine Core: Build underlying byte stream processing and Abstract Syntax Tree (AST) for rules.

[ ] Phase 2: Model Integration: Seamlessly integrate the custom-trained AI model with the parsing engine.

[ ] Phase 3: Standard APIs: Provide multi-protocol data output interfaces (HTTP / MQTT / WebSocket).

[ ] Phase 4: Developer CLI: Release CLI tools for local payload testing and model fine-tuning.

[ ] Phase 5: Alpha Release: First usable version with out-of-the-box support for mainstream industrial gateway devices.

🤝 Contributing

We welcome developers interested in IIoT, protocol reverse-engineering, and AI edge computing to join the discussion! Feel free to open an Issue to chat with us.

📄 License

This project is licensed under the Apache License 2.0.
