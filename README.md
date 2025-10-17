# Flink Tutorial Template

目标
- 提供面向入门与工程化的 Apache Flink 教程模板（中文）。
- 包含 Java / Scala / PyFlink 最小可运行示例、Docker Compose 快速运行堆栈、Kubernetes manifests、GitHub Actions CI、文档与练习。

主要目录
- examples/java/wordcount — Java DataStream WordCount 最小示例
- examples/scala/wordcount — Scala DataStream WordCount 最小示例
- examples/python/pywordcount — PyFlink 最小示例
- docker/ — docker-compose.yml（Flink + Kafka + Zookeeper）与说明
- k8s/ — Kubernetes manifests（基础 session-cluster + job submit）
- docs/ — 快速启动 / 概念 / 生产化指南 / 练习
- .github/workflows/ — CI（构建与 smoke tests）

快速开始（本地，Docker Compose）
1. 克隆仓库
   git clone https://github.com/784755850/flink-tutorial-template.git
2. 启动依赖堆栈（Flink + Kafka + Zookeeper）
   cd docker
   docker-compose up -d
3. Java 示例（Socket WordCount）
   cd examples/java/wordcount
   mvn -DskipTests package
   在 Flink Web UI（http://localhost:8081）提交 target/*.jar，或使用 CLI 提交。
4. PyFlink 示例
   cd examples/python/pywordcount
   pip install -r requirements.txt
   python pywordcount.py --jobmanager localhost:8081

课程建议（顺序）
- 入门：概念、Execution Mode、DataStream vs Table API、简单 WordCount
- 进阶：State、Window、Time、Watermarks、Checkpoint、Exactly-once
- 实战：Kafka → Flink → 数据湖（Iceberg/Paimon）写入、监控、调优、生产化部署（k8s）

贡献
- 欢迎 Issue / PR / 课程内容与练习。
- 参见 docs/CONTRIBUTING.md（后续补充）

许可证
- Apache-2.0