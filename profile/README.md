# 🛍️ YuanShop · 微服务电商学习套件

&gt; 一个为 **Java 学习者** 打造的云原生电商脚手架，  
&gt; 用 **Spring Cloud** 拆服务，用 **Docker** 一键起飞，用 **GitHub Actions** 自动交付。  
&gt; *Learning by Building, Ship on Day 30.*

---

## ✨ 30 秒速览
| Topic | Tech |
|-------|------|
| 网关 & 安全 | Spring Cloud Gateway + JWT |
| 注册/配置 | Nacos 2.3 |
| 微服务 | Spring Boot 3.2 + OpenFeign |
| 数据 | MySQL 8（独立 schema）+ Redis + MyBatis-Plus |
| 消息 | RabbitMQ |
| 搜索 | Elasticsearch |
| 监控 | SkyWalking + Prometheus + Grafana |
| 部署 | Docker Compose & Kubernetes 就绪 |
| CI/CD | GitHub Actions → GHCR |
| 前端 | Vue3 + Element-Plus + Vite |

---

## 🧩 组织仓库一览
| Repo | 简介 |
|------|------|
| [mall-gateway](https://github.com/YuanShop/mall-gateway) | 统一网关 + 全局鉴权 |
| [mall-user-service](https://github.com/YuanShop/mall-user-service) | 用户注册/登录/JWT |
| [mall-product-service](https://github.com/YuanShop/mall-product-service) | 商品 & SKU |
| [mall-stock-service](https://github.com/YuanShop/mall-stock-service) | 库存预扣 & 解锁 |
| [mall-order-service](https://github.com/YuanShop/mall-order-service) | 订单生命周期 |
| [mall-search-service](https://github.com/YuanShop/mall-search-service) | ES 商品搜索 |
| [mall-front](https://github.com/YuanShop/mall-front) | Vue3 管理后台 |
| [mall-docker](https://github.com/YuanShop/mall-docker) | 一键 `docker-compose up` 脚本与监控配置 |
| [mall-common](https://github.com/YuanShop/mall-common) | 公共工具、统一响应、雪花 ID |

&gt; 🔍 更多子项目陆续上线，Follow 不迷路！

---

## 🚀 5 步本地跑通
```bash
# 1. 克隆组织（示例）
gh repo clone YuanShop/mall-docker && cd mall-docker

# 2. 启动基础组件
docker-compose -f infra.yml up -d

# 3. 依次启动微服务（IDEA / VSCode）
#    gateway → user → product → stock → order

# 4. 导入 SQL
mysql -uroot -p &lt; sql/init_all_schema.sql

# 5. 启动前端
cd ../mall-front && npm i && npm run dev
# 浏览器访问 http://localhost:5173
```

---

📊 架构图
<!-- 用 draw.io 导出 SVG，放到 mall-docker/docs/arch.svg -->
https://raw.githubusercontent.com/YuanShop/mall-docker/main/docs/arch.svg

🌟 亮点

✅ DDD 严格分库 —— 0 跨库 JOIN，拒绝分布式单体

✅ 最终一致性 —— 本地消息表 + RabbitMQ，订单库存对账

✅ 横向越权防护 —— Gateway 统一验 JWT，下游只认 X-Auth-User

✅ 全链路观测 —— SkyWalking TraceId 贯穿 5 个服务

✅ GitHub Actions 自动交付 —— Push 即构建镜像并推送 GHCR

✅ K8s 就绪 —— /k8s 目录含 Helm 模板，可无缝迁云

📌 RoadMap

[x] MVP：注册/登录/商品/下单/库存

[x] Docker Compose 一键启动

[x] SkyWalking + Prometheus 监控

[ ] 分库分表（ShardingSphere）

[ ] 支付中心（支付宝沙箱）

[ ] 秒杀 & 消息削峰（Sentinel + RocketMQ）

[ ] Helm 发布到 Kubernetes

🤝 贡献

Fork 任意仓库

新建 feat/xxx 分支

提交 PR，CI 自动检查

等待 Review & Merge

💬 联系我

Issue/Discussions：随时提

邮箱：3205518128@qq.com

个人主页：[https://github.com/huangyuan](https://github.com/HuangYuan1024)

📈 统计

https://visitor-badge.laobi.icu/badge?page_id=YuanShop

https://img.shields.io/github/stars/YuanShop/mall-gateway?style=social https://img.shields.io/github/forks/YuanShop/mall-gateway?style=social

如果对你有帮助，记得 ⭐ Star  &  👀 Follow 哦！
