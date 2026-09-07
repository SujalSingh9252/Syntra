<div align="center">

# ⚡ Syntra

### Distributed Real-Time Observability & Monitoring Platform

*A lightweight, agent-based platform for monitoring host systems and Docker containers in real time.*

<br/>

[![React](https://img.shields.io/badge/Frontend-React-61DAFB?logo=react\&logoColor=white)](https://react.dev/)
[![Node.js](https://img.shields.io/badge/Backend-Node.js-339933?logo=node.js\&logoColor=white)](https://nodejs.org/)
[![PostgreSQL](https://img.shields.io/badge/Database-PostgreSQL-4169E1?logo=postgresql\&logoColor=white)](https://www.postgresql.org/)
[![Socket.IO](https://img.shields.io/badge/Real--Time-Socket.IO-010101?logo=socketdotio\&logoColor=white)](https://socket.io/)
[![Docker](https://img.shields.io/badge/DevOps-Docker-2496ED?logo=docker\&logoColor=white)](https://www.docker.com/)

<br/>

**Monitor. Observe. Analyze. React.**

</div>

---

## 📌 Overview

**Syntra** is a distributed, real-time observability and monitoring platform designed to monitor **host systems** and **Docker containers** from a centralized dashboard.

The platform follows an **agent-based architecture**, where a lightweight monitoring agent runs on each system, collects system and container metrics, and sends them to a centralized backend.

The backend processes and stores monitoring data in **PostgreSQL**, broadcasts live updates through **Socket.IO**, and powers an interactive **React dashboard** for real-time visualization and analysis.

> Syntra provides a foundation for building scalable infrastructure monitoring and observability systems.

---

## ✨ Key Features

### 🖥️ Host System Monitoring

Monitor essential system resources in real time:

* ⚡ CPU Usage
* 🧠 Memory Usage
* ⏱️ System Uptime
* 🟢 Online / Offline Status
* 📊 Historical System Metrics

---

### 🐳 Docker Container Monitoring

Track Docker containers running on monitored systems:

* 📦 Container Status
* ⚡ Per-Container CPU Usage
* 🧠 Per-Container Memory Usage
* 🔄 Real-Time Container Updates

---

### 🚨 Intelligent Alerts

Stay informed when system resources exceed defined thresholds:

* 🔴 High CPU Usage Alerts
* 🟠 High Memory Usage Alerts
* ⚙️ Threshold-Based Monitoring

---

### 📡 Real-Time Observability

Syntra uses **Socket.IO** to deliver live monitoring updates.

* ⚡ Instant Metric Updates
* 🔄 Real-Time Dashboard Synchronization
* 📊 Live System Monitoring
* 🌐 Multi-System Support

---

### 💾 Persistent Metrics Storage

Monitoring data is stored using **PostgreSQL**.

This enables:

* Historical Metric Analysis
* System Monitoring Records
* Persistent Infrastructure Data
* Future Analytics & Reporting

---

## 🏗️ System Architecture

```text
                         ┌─────────────────────┐
                         │   Monitored System  │
                         │                     │
                         │  Host + Docker      │
                         └──────────┬──────────┘
                                    │
                                    ▼
                         ┌─────────────────────┐
                         │ Lightweight Agent   │
                         │                     │
                         │ • CPU               │
                         │ • Memory            │
                         │ • Uptime            │
                         │ • Docker Metrics    │
                         └──────────┬──────────┘
                                    │
                              REST API
                                    │
                                    ▼
                    ┌───────────────────────────┐
                    │     Express Backend       │
                    │                           │
                    │ • Process Metrics         │
                    │ • Alert Detection         │
                    │ • System Management       │
                    └─────────────┬─────────────┘
                                  │
                    ┌─────────────┴─────────────┐
                    │                           │
                    ▼                           ▼
          ┌──────────────────┐       ┌──────────────────┐
          │   PostgreSQL     │       │    Socket.IO     │
          │                  │       │                  │
          │ Persistent Data  │       │ Real-Time Events │
          └────────┬─────────┘       └────────┬─────────┘
                   │                          │
                   └────────────┬─────────────┘
                                │
                                ▼
                    ┌───────────────────────────┐
                    │      React Dashboard      │
                    │                           │
                    │ • Live Metrics            │
                    │ • System Status           │
                    │ • Docker Monitoring       │
                    │ • Historical Charts       │
                    │ • Alerts                  │
                    └───────────────────────────┘
```

---

## 🔄 How Syntra Works

### 1️⃣ Monitoring Agent

A lightweight monitoring agent runs on each monitored machine.

The agent collects:

```text
Host Metrics
│
├── CPU Usage
├── Memory Usage
└── System Uptime

Docker Metrics
│
├── Container Status
├── CPU Usage
└── Memory Usage
```

---

### 2️⃣ Metrics Collection

The agent continuously collects system and Docker metrics using:

* `systeminformation`
* `dockerode`

---

### 3️⃣ Backend Processing

The collected metrics are sent to the centralized backend through REST APIs.

The backend is responsible for:

* Processing incoming metrics
* Managing monitored systems
* Detecting threshold violations
* Storing historical data
* Broadcasting real-time updates

---

### 4️⃣ Data Storage

Metrics are persisted in **PostgreSQL** for historical monitoring and future analysis.

---

### 5️⃣ Real-Time Communication

The backend broadcasts live monitoring events using:

```text
Socket.IO
```

This allows connected dashboards to receive updates without continuously polling the server.

---

### 6️⃣ Monitoring Dashboard

The React dashboard provides a centralized view of the infrastructure.

Users can monitor:

* 🖥️ Host Systems
* 📊 CPU Usage
* 🧠 Memory Usage
* 🐳 Docker Containers
* 🚨 System Alerts
* 📈 Historical Metrics
* 🟢 System Availability

---

# 🛠️ Tech Stack

## 🎨 Frontend

| Technology       | Purpose            |
| ---------------- | ------------------ |
| React            | User Interface     |
| Recharts         | Data Visualization |
| Axios            | API Communication  |
| Socket.IO Client | Real-Time Updates  |
| Vite             | Frontend Tooling   |

---

## ⚙️ Backend

| Technology | Purpose                 |
| ---------- | ----------------------- |
| Node.js    | Runtime Environment     |
| Express.js | REST API                |
| PostgreSQL | Database                |
| Socket.IO  | Real-Time Communication |

---

## 📡 Monitoring Agent

| Technology        | Purpose               |
| ----------------- | --------------------- |
| Node.js           | Agent Runtime         |
| systeminformation | Host Metrics          |
| dockerode         | Docker Monitoring     |
| Axios             | Backend Communication |

---

## 🐳 DevOps

| Technology     | Purpose                     |
| -------------- | --------------------------- |
| Docker         | Containerization            |
| Docker Compose | Multi-Service Orchestration |

---

# 📂 Project Structure

```text
Syntra
│
├── 📁 agent
│   │
│   ├── index.js
│   ├── main.js
│   ├── package.json
│   └── .env.example
│
├── 📁 backend
│   │
│   ├── 📁 src
│   │   │
│   │   ├── 📁 config
│   │   │   └── db.js
│   │   │
│   │   ├── 📁 controllers
│   │   │   └── metricsController.js
│   │   │
│   │   ├── 📁 routes
│   │   │   └── metricsRoutes.js
│   │   │
│   │   ├── app.js
│   │   ├── server.js
│   │   └── socket.js
│   │
│   ├── Dockerfile
│   ├── schema.sql
│   └── package.json
│
├── 📁 frontend
│   │
│   ├── 📁 public
│   ├── 📁 src
│   │
│   ├── Dockerfile
│   └── package.json
│
├── docker-compose.yml
│
└── README.md
```

---

# 🚀 Getting Started

## Prerequisites

Make sure you have the following installed:

* Node.js
* npm
* PostgreSQL
* Docker
* Docker Compose

Check your installations:

```bash
node --version
npm --version
docker --version
```

---

# ⚙️ Installation

## 1. Clone the Repository

```bash
git clone https://github.com/SujalSingh9252/Syntra.git
```

Move into the project:

```bash
cd Syntra
```

---

# 🗄️ Backend Setup

Navigate to the backend directory:

```bash
cd backend
```

Install dependencies:

```bash
npm install
```

Create your environment file:

```bash
copy .env.example .env
```

Configure your database credentials inside `.env`.

Initialize the PostgreSQL database using:

```bash
schema.sql
```

Start the backend:

```bash
npm run dev
```

---

# 🎨 Frontend Setup

Navigate to the frontend directory:

```bash
cd frontend
```

Install dependencies:

```bash
npm install
```

Start the development server:

```bash
npm run dev
```

The dashboard will typically be available at:

```text
http://localhost:5173
```

---

# 📡 Monitoring Agent Setup

Navigate to the agent directory:

```bash
cd agent
```

Install dependencies:

```bash
npm install
```

Create your environment file:

```bash
copy .env.example .env
```

Start the monitoring agent:

```bash
node main.js
```

The agent will begin collecting and sending system metrics to the backend.

---

# 🐳 Docker Deployment

Syntra includes Docker configuration for containerized deployment.

From the project root:

```bash
docker compose up --build
```

To run containers in detached mode:

```bash
docker compose up -d
```

Stop all services:

```bash
docker compose down
```

---

# 📊 Monitoring Capabilities

| Feature                     | Supported |
| --------------------------- | --------- |
| Host CPU Monitoring         | ✅         |
| Host Memory Monitoring      | ✅         |
| System Uptime               | ✅         |
| Docker Container Monitoring | ✅         |
| Container CPU Metrics       | ✅         |
| Container Memory Metrics    | ✅         |
| Container Status            | ✅         |
| Multi-System Monitoring     | ✅         |
| Online / Offline Detection  | ✅         |
| Real-Time Updates           | ✅         |
| Historical Metrics          | ✅         |
| Threshold Alerts            | ✅         |
| PostgreSQL Storage          | ✅         |

---

# 🔐 Environment Variables

Create `.env` files based on the provided `.env.example` files.

Example configuration:

```env
PORT=5000

DB_HOST=localhost
DB_PORT=5432
DB_NAME=syntra
DB_USER=postgres
DB_PASSWORD=your_password
```

> ⚠️ Never commit your `.env` files or database credentials to GitHub.

---

# 🎯 Project Goals

Syntra was built to explore and implement concepts related to:

* Distributed Systems
* Observability
* Real-Time Systems
* Agent-Based Architecture
* WebSockets
* Infrastructure Monitoring
* Docker Monitoring
* System Metrics Collection
* Data Visualization
* Containerization

---

# 🔮 Roadmap

## ✅ Version 0 — Completed

The initial version of Syntra includes:

* [x] Host System Monitoring
* [x] Docker Container Monitoring
* [x] Real-Time Dashboard
* [x] Socket.IO Communication
* [x] PostgreSQL Storage
* [x] Threshold-Based Alerts
* [x] Historical Metrics
* [x] Multi-System Monitoring
* [x] Docker Support

---

## 🚧 Version 1 — In Progress

Planned improvements:

* [ ] Authentication & Authorization
* [ ] Advanced Alert Notifications
* [ ] Advanced Analytics and monitoring dashboards
* [ ] Cloud Deployment
* [ ] Improved Scalability


---

# 💡 Future Vision
While Syntra currently focuses on real-time host system and Docker container monitoring, the platform can be extended in the future to support additional infrastructure and observability capabilities:

🖥️ Host Systems
      ↓
🐳 Docker Containers
      ↓
☸️ Kubernetes Monitoring
      ↓
☁️ Cloud Infrastructure
      ↓
📊 Centralized Observability

Potential enhancements could include advanced alerting, authentication, and support for larger-scale infrastructure monitoring.

---

# 🤝 Contributing

Contributions, ideas, and improvements are welcome.

Feel free to:

* Fork the repository
* Create a feature branch
* Submit a pull request
* Open an issue

---

# 📄 License

This project is currently developed for learning, experimentation, and portfolio purposes.

---

<div align="center">

## ⚡ Built with a focus on Real-Time Systems, Distributed Architecture & Observability

### ⭐ If you found this project interesting, consider giving it a star!

<br/>

### 👨‍💻 Developed by Sujal Singh

**B.Tech CSE (Hons.) — AI & Analytics**

🔗 GitHub: https://github.com/SujalSingh9252

---

**Syntra — Monitor. Observe. Analyze. React. ⚡**

</div>


