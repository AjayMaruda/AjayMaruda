<div align="center">

# Ajay Maruda

### Backend Software Engineer

Building APIs, data models and background-processing pipelines in **Node.js** and **TypeScript**

<br>

![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=nodedotjs&logoColor=white)
![NestJS](https://img.shields.io/badge/NestJS-E0234E?style=flat-square&logo=nestjs&logoColor=white)
![Express](https://img.shields.io/badge/Express-000000?style=flat-square&logo=express&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=flat-square&logo=mongodb&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)

[LinkedIn](https://linkedin.com/in/ajay-maruda) &nbsp;·&nbsp; Ahmedabad, India &nbsp;·&nbsp; Open to Backend / Software Engineer roles

</div>

<br>

## About

I build REST APIs and backend services with NestJS and Express, with a focus on authentication, data modeling across PostgreSQL and MongoDB, and background processing with job queues. I started in data and reporting (Power BI dashboards) before moving into backend development.

Most of my professional work lives in private repositories, so the projects below are my public examples.

|  |  |
|---|---|
| **Experience** | About a year building and maintaining backend services |
| **Focus** | REST APIs, JWT/RBAC auth, SQL and document databases, queue-based workers |
| **Also built** | Docker and Kubernetes manifests, and a Vue 3 client for my own API |
| **Now building** | A document-processing pipeline with a job queue and an LLM API |
| **Now learning** | Python for ML, LLM applications, AWS deployment, CI/CD |

<br>

## Featured Projects

### Beacon: centralized log ingestion for microservices

![NestJS](https://img.shields.io/badge/NestJS-E0234E?style=flat-square&logo=nestjs&logoColor=white)
![Express](https://img.shields.io/badge/Express-000000?style=flat-square&logo=express&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=flat-square&logo=mongodb&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=flat-square&logo=kubernetes&logoColor=white)

A lightweight, self-hosted way to collect logs from several services in one place and query them by service name and log level.

```mermaid
flowchart LR
    S["Services<br>(auth, orders, payments)"] -->|POST /logs| I["Ingestor<br>NestJS"]
    I --> M[("MongoDB<br>logs")]
    H["Health service<br>Express"] --> P[("PostgreSQL<br>service registry")]
    K["Kubernetes HPA<br>2 to 5 pods"] -.-> I
```

- NestJS ingestor stores logs in MongoDB; a separate Express service keeps a service registry in PostgreSQL and exposes a health endpoint
- Multi-stage Dockerfiles and Swagger docs for both services; the whole stack runs with `docker compose up`
- Kubernetes manifests (ConfigMap, Secret, Ingress) with an HPA that scales the ingestor from 2 to 5 pods on CPU load

**[View repository](https://github.com/AjayMaruda/beacon)**

<br>

### AI Document Intelligence Platform &nbsp;`in progress`

![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white)
![BullMQ](https://img.shields.io/badge/BullMQ-FF4500?style=flat-square&logoColor=white)
![OpenAI](https://img.shields.io/badge/OpenAI_API-412991?style=flat-square&logo=openai&logoColor=white)

A backend for uploading documents and extracting structured data from PDFs with an LLM.

```mermaid
flowchart LR
    C["Client"] -->|upload| A["API<br>Express + JWT"]
    A --> O[("MinIO<br>files")]
    A --> D[("PostgreSQL<br>Prisma")]
    A -->|enqueue| Q[("Redis<br>BullMQ")]
    Q --> W["Worker"]
    W -->|extract| L["OpenAI API"]
```

- Extraction runs in a separate BullMQ worker process, so uploads never block on AI calls
- JWT-protected API with Zod validation, Helmet and structured logging with Pino
- Status: core pipeline under active development; architecture and setup docs are being written

**[View repository](https://github.com/AjayMaruda/ai-doc-intelligence-platform)**

<br>

### Event Booking System: REST API + Vue client

![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=nodedotjs&logoColor=white)
![Express](https://img.shields.io/badge/Express-000000?style=flat-square&logo=express&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=flat-square&logo=mongodb&logoColor=white)
![JWT](https://img.shields.io/badge/JWT-000000?style=flat-square&logo=jsonwebtokens&logoColor=white)
![Swagger](https://img.shields.io/badge/Swagger-85EA2D?style=flat-square&logo=swagger&logoColor=black)
![Vue.js](https://img.shields.io/badge/Vue_3-4FC08D?style=flat-square&logo=vuedotjs&logoColor=white)

A booking backend with role-based access, seat tracking and an admin export.

```mermaid
flowchart LR
    R["Request"] --> L["Rate limiter"] --> J["JWT auth"] --> G{"Role"}
    G -->|user| B["Booking routes"]
    G -->|admin| E["Event admin + CSV export"]
    B --> DB[("MongoDB")]
    E --> DB
```

- JWT authentication with admin/user roles enforced in middleware; passwords hashed with bcrypt
- Seat availability updates on booking and is restored on cancellation
- Rate limiting on auth and booking routes, input validation, event filtering and pagination, Swagger docs
- Vue 3 client with Pinia, Vue Router and Tailwind, including a role-based UI

**[Backend repository](https://github.com/AjayMaruda/event-booking-system)** &nbsp;·&nbsp; **[Frontend repository](https://github.com/AjayMaruda/event-booking-frontend)**

<br>

## Tech Stack

| | |
|---|---|
| **Languages** | TypeScript, JavaScript, SQL |
| **Backend** | Node.js, NestJS, Express, REST, Swagger/OpenAPI |
| **Auth and validation** | JWT, bcrypt, Zod, express-validator, rate limiting |
| **Databases** | PostgreSQL (Prisma, Sequelize), MongoDB (Mongoose), Redis |
| **Queues** | BullMQ |
| **Containers** | Docker, Docker Compose, Kubernetes manifests with HPA (local, Minikube) |
| **Tooling** | Git, ESLint, Prettier, Husky |
| **Frontend (secondary)** | Vue 3, Pinia, Vue Router, Tailwind CSS | Reactjs | Nextjs |
| **Data and reporting** | Power BI |

**Currently learning**

![Python](https://img.shields.io/badge/Python-6B7280?style=flat-square&logo=python&logoColor=white)
![LLM apps](https://img.shields.io/badge/LLM_apps_%26_RAG-6B7280?style=flat-square)
![AWS](https://img.shields.io/badge/AWS-6B7280?style=flat-square&logo=amazonwebservices&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-6B7280?style=flat-square&logo=githubactions&logoColor=white)

<br>

## Engineering Interests

- Backend architecture and API design
- Background processing and queue-based workflows
- Database design across SQL and document stores
- Containerized deployments and Kubernetes basics
- AI-powered applications built on solid backend foundations

<br>

<div align="center">

**[LinkedIn](https://linkedin.com/in/ajay-maruda)**

</div>
