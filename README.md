<div align="center">

<!-- Decorative banner — no text inside so fallback never breaks the name -->
<img src="https://capsule-render.vercel.app/api?type=waving&color=0:007979,50:005f5f,100:003d3d&height=140&section=header" width="100%"/>

<!-- Name always renders as HTML — never dependent on capsule-render -->
<h1>
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=700&size=40&pause=1000&color=ffffff&center=true&vCenter=true&width=500&lines=Ajay+Maruda" alt="Ajay Maruda" />
</h1>

<h3>⚙️ Backend & Platform Engineer</h3>

<p>
  <em>Building systems that hold up under pressure —<br/>
  distributed infrastructure · async pipelines · cloud-native backends</em>
</p>

<br/>

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://linkedin.com/in/ajay-maruda)
[![Gmail](https://img.shields.io/badge/Gmail-D14836?style=flat-square&logo=gmail&logoColor=white)](mailto:ajaymarooda@email.com)
![Profile Views](https://komarev.com/ghpvc/?username=AjayMaruda&style=flat-square&color=007979&label=PROFILE+VIEWS)

</div>

---

## 👤 About Me

Backend engineer with a platform mindset. I work primarily in **Node.js / TypeScript**, and I think about systems the way an operator would — not just *"does it work"* but *"will it hold up at 3am when load spikes and someone's paging you."*

- 🏗️ **Core Systems** — Scalable backend services, event-driven distributed architectures, cloud-native infrastructure
- 🔭 **Observability** — Structured logging, custom metric collectors, distributed tracing, health monitoring
- 🌱 **Currently** — Building an AI document processing pipeline with BullMQ workers, Redis caching, and K8s on AWS

📍 **Ahmedabad, India** &nbsp;·&nbsp; 🌎 Open to Backend, Platform, and Cloud Engineering roles &nbsp;·&nbsp; 💼 Remote-friendly

---

## 📐 Engineering Principles

> [!IMPORTANT]
> System design decisions prioritize architectural integrity, reliable failure modes, and automated reproducibility over manual operations.

| Principle | Practice |
|-----------|----------|
| 🏛️ **Architecture First** | Explicit loose coupling between layers; core services stay independent |
| 🛡️ **Reliability Matters** | Systems expect, isolate, and recover from runtime faults gracefully |
| 🔍 **Observability by Default** | First-class tracing, telemetry metrics, and structured logging from day one |
| 🤖 **Automation Over Manual** | CI/CD pipelines and declarative IaC eliminate operational overhead |
| 📄 **Document as You Build** | Swagger specs, `.env.example`, and architecture diagrams ship with the code |

---

## ⚡ Tech Stack

<div align="center">

**Backend & Runtime**

![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=node.js&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![NestJS](https://img.shields.io/badge/NestJS-E0234E?style=flat-square&logo=nestjs&logoColor=white)
![Express](https://img.shields.io/badge/Express-000000?style=flat-square&logo=express&logoColor=white)

**Databases & Caching**

![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=flat-square&logo=mongodb&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white)
![Prisma](https://img.shields.io/badge/Prisma-2D3748?style=flat-square&logo=prisma&logoColor=white)

**Infrastructure & Cloud**

![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=flat-square&logo=kubernetes&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazon-aws&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=github-actions&logoColor=white)

**Tooling & Observability**

![BullMQ](https://img.shields.io/badge/BullMQ-FF4500?style=flat-square&logo=redis&logoColor=white)
![Swagger](https://img.shields.io/badge/Swagger-85EA2D?style=flat-square&logo=swagger&logoColor=black)
![ESLint](https://img.shields.io/badge/ESLint-4B32C3?style=flat-square&logo=eslint&logoColor=white)
![Husky](https://img.shields.io/badge/Husky-000000?style=flat-square&logo=git&logoColor=white)

</div>

---

## 📂 Featured Projects & Production Architecture

> [!NOTE]
> Each system below was engineered around asynchronous scaling, distributed state, and high availability — not just functional correctness.

---

### 🔦 1. [Beacon](https://github.com/AjayMaruda/beacon) — Centralized Log Ingestion Platform

*A self-hosted observability platform engineered to collect, store, and verify system health logs across distinct microservices.*

| Feature | Detail |
|---------|--------|
| ⚖️ **Elastic Scaling** | Kubernetes HPA scales ingestion pods 2 → 5 dynamically under load |
| 🗄️ **Storage Isolation** | Dual-database: hot telemetry to MongoDB · relational ledger to PostgreSQL |
| 💓 **Service Integrity** | Dedicated health monitor verifies ingestion pipeline availability continuously |

```mermaid
flowchart TD
    A[Client Applications] -->|Log Ingestion Streams| B[NestJS Ingestion Core]
    F[Kubernetes HPA Engine] -.->|Auto Scales 2 to 5 Pods| B
    B -->|Structured Schema| C[(MongoDB Cluster)]
    B -->|Relational Ledger| D[(PostgreSQL)]
    B <-->|Heartbeat Tracking| E[Isolated Health Monitor]
    style B fill:#007979,stroke:#004d4d,stroke-width:2px,color:#fff
    style F fill:#1e293b,stroke:#334155,stroke-width:1px,color:#fff
    style C fill:#47A248,stroke:#2d6b2d,stroke-width:1px,color:#fff
    style D fill:#4169E1,stroke:#2a4aad,stroke-width:1px,color:#fff
    style E fill:#5f6b7c,stroke:#3d4a57,stroke-width:1px,color:#fff
```

![NestJS](https://img.shields.io/badge/NestJS-E0234E?style=flat-square&logo=nestjs&logoColor=white)
![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=flat-square&logo=kubernetes&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=flat-square&logo=mongodb&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![Swagger](https://img.shields.io/badge/Swagger-85EA2D?style=flat-square&logo=swagger&logoColor=black)

---

### 📅 2. [Event Booking System](https://github.com/AjayMaruda/event-booking-system) — Production-grade Booking API

*A full-featured backend API built around secure access control, atomic state transitions, and production-conscious reliability.*

| Feature | Detail |
|---------|--------|
| 🔐 **Access Control** | JWT auth + RBAC (Admin / User) enforced at the middleware layer |
| ⚛️ **Atomic Transactions** | Seat booking and cancellation are fully atomic — inventory always consistent |
| 🚧 **Abuse Prevention** | Rate limiting on auth routes prevents brute-force and credential-stuffing |

```mermaid
flowchart TD
    A[API Client] -->|Request| B[Rate Limiter]
    B -->|Passed| C[JWT Auth Layer]
    C -->|Token Valid| D{RBAC Guard}
    D -->|Admin Role| E[Admin Routes\nCSV Export · Analytics]
    D -->|User Role| F[Booking Routes]
    F -->|Atomic Lock| G[(MongoDB\nSeat State)]
    F -->|On Cancel| G
    style C fill:#007979,stroke:#004d4d,stroke-width:2px,color:#fff
    style D fill:#1e293b,stroke:#334155,stroke-width:1px,color:#fff
    style G fill:#47A248,stroke:#2d6b2d,stroke-width:1px,color:#fff
    style B fill:#DC2626,stroke:#991b1b,stroke-width:1px,color:#fff
```

![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=node.js&logoColor=white)
![Express](https://img.shields.io/badge/Express-000000?style=flat-square&logo=express&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=flat-square&logo=mongodb&logoColor=white)
![JWT](https://img.shields.io/badge/JWT-000000?style=flat-square&logo=jsonwebtokens&logoColor=white)
![Swagger](https://img.shields.io/badge/Swagger-85EA2D?style=flat-square&logo=swagger&logoColor=black)

---

### 🤖 3. [AI Doc Intelligence Platform](https://github.com/AjayMaruda/ai-doc-intelligence-platform) — Async AI Processing Pipeline *(active)*

*A cloud-native document processing system designed for high-throughput async extraction, distributed caching, and full AWS deployment.*

| Feature | Detail |
|---------|--------|
| 🔄 **Async Workers** | BullMQ decouples ingestion from processing — each stage scales independently |
| ⚡ **Distributed Cache** | Redis reduces redundant AI API calls and cuts repeat-document latency |
| ☁️ **Cloud-Native** | Fully containerized on AWS EKS with RDS, S3, and ElastiCache |

```mermaid
flowchart TD
    A[Document Upload] -->|Store| B[(S3 Bucket)]
    A -->|Enqueue Job| C[BullMQ Worker Queue]
    C -->|Process| D[AI Extraction Engine\nOpenAI API]
    D -->|Cache Hit?| E{Redis\nElastiCache}
    E -->|Miss — Persist| F[(PostgreSQL\nRDS via Prisma)]
    E -->|Hit — Return| G[Response]
    H[Kubernetes EKS] -.->|Orchestrates| C
    H -.->|Orchestrates| D
    style D fill:#007979,stroke:#004d4d,stroke-width:2px,color:#fff
    style H fill:#1e293b,stroke:#334155,stroke-width:1px,color:#fff
    style E fill:#DC382D,stroke:#991b1b,stroke-width:1px,color:#fff
    style F fill:#4169E1,stroke:#2a4aad,stroke-width:1px,color:#fff
    style B fill:#FF9900,stroke:#cc7a00,stroke-width:1px,color:#fff
```

![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![BullMQ](https://img.shields.io/badge/BullMQ-FF4500?style=flat-square&logo=redis&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white)
![Prisma](https://img.shields.io/badge/Prisma-2D3748?style=flat-square&logo=prisma&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazon-aws&logoColor=white)
![OpenAI](https://img.shields.io/badge/OpenAI-412991?style=flat-square&logo=openai&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)

---

## 📊 GitHub Activity

<div align="center">

[![GitHub Streak](https://streak-stats.demolab.com?user=AjayMaruda&theme=dark&hide_border=true&background=0D1117&ring=007979&fire=007979&currStreakLabel=007979&sideLabels=888888&dates=888888)](https://github.com/AjayMaruda)

</div>

> 💡 Most active development occurs in private repositories and client engagements. Public repositories represent production architecture patterns — engineered for real-world constraints, not toy examples.

---

<div align="center">

[![Let's Connect](https://img.shields.io/badge/Let's_Connect_on_LinkedIn-007979?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/ajay-maruda)

<br/>

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:003d3d,50:005f5f,100:007979&height=100&section=footer" width="100%"/>

</div>
