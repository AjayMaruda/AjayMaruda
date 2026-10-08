# Ajay Maruda

**Backend Software Engineer** · Node.js · TypeScript · PostgreSQL · MongoDB
Ahmedabad, India · [LinkedIn](https://linkedin.com/in/ajay-maruda)

I build REST APIs and backend services with NestJS and Express, focusing on authentication, data modeling across PostgreSQL and MongoDB, and background processing with job queues. I started in data and reporting (Power BI dashboards) before moving into backend development. I'm currently building a document-processing pipeline around a job queue and an LLM API, and learning Python for ML.

Most of my professional work is in private repositories, so the projects below are my public examples.

---

## About

- About a year of professional experience building and maintaining backend services in TypeScript and Node.js
- Comfortable with both relational (PostgreSQL) and document (MongoDB) data models
- Built JWT authentication with role-based access control, request validation, and rate limiting
- Built a multi-service system packaged with Docker and Kubernetes manifests
- Built one Vue 3 frontend for my own API; backend is my main focus
- Currently learning: Python for ML, building LLM-based extraction, and deploying to AWS

---

## Tech Stack

**Hands-on**

| Area | Tools |
|---|---|
| Languages | TypeScript, JavaScript, SQL |
| Backend | Node.js, NestJS, Express, REST, Swagger/OpenAPI |
| Auth and validation | JWT, bcrypt, Zod, express-validator, rate limiting |
| Databases | PostgreSQL (Prisma, Sequelize), MongoDB (Mongoose), Redis |
| Queues | BullMQ |
| Containers | Docker, Docker Compose, Kubernetes manifests with HPA (local, Minikube) |
| Tooling | Git, ESLint, Prettier, Husky |
| Frontend (secondary) | Vue 3, Pinia, Vue Router, Tailwind CSS |
| Data and reporting | Power BI |

**Currently learning:** Python and ML fundamentals · LLM applications (extraction first, then RAG) · AWS deployment · CI/CD with GitHub Actions

---

## Featured Projects

### [Beacon](https://github.com/AjayMaruda/beacon): centralized log ingestion for microservices
**Technology:** `NestJS` · `Express` · `TypeScript` · `MongoDB` · `PostgreSQL` · `Docker` · `Kubernetes`

- A NestJS ingestor service accepts logs from multiple services and stores them in MongoDB, queryable by service name and log level
- A separate Express service keeps a service registry in PostgreSQL and exposes a health endpoint
- Both services have multi-stage Dockerfiles and Swagger docs, and the whole stack runs with one `docker compose up`
- Kubernetes manifests (ConfigMap, Secret, Ingress) include an HPA that scales the ingestor from 2 to 5 pods on CPU load

### [AI Document Intelligence Platform](https://github.com/AjayMaruda/ai-doc-intelligence-platform): in progress
**Technology:** `TypeScript` · `Express` · `PostgreSQL` · `Prisma` · `Redis` · `BullMQ` · `MinIO` · `OpenAI API`

- Backend for uploading documents and extracting structured data from PDFs with an LLM
- Extraction runs in a separate BullMQ worker process, so uploads don't block on AI calls
- JWT-protected API with Zod validation, Helmet and structured logging with Pino
- Status: core pipeline under active development; architecture and setup docs are being written

### [Event Booking System](https://github.com/AjayMaruda/event-booking-system): REST API
**Technology:** `Node.js` · `Express` · `MongoDB` · `JWT` · `Swagger`

- JWT authentication with admin/user roles enforced in middleware
- Seat availability updates on booking and is restored on cancellation
- Rate limiting on auth and booking routes, input validation, and Swagger docs
- Event filtering and pagination, plus admin CSV export of bookings
- Vue 3 client: [event-booking-frontend](https://github.com/AjayMaruda/event-booking-frontend) (Pinia, Vue Router, Tailwind, role-based UI)

---

## Engineering Interests

- Backend architecture and API design
- Background processing and queue-based workflows
- Database design across SQL and document stores
- Containerized deployments and Kubernetes basics
- AI-powered applications built on top of solid backend foundations

---

## Contact

[LinkedIn](https://linkedin.com/in/ajay-maruda)
