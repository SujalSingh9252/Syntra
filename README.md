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

The platform follows an **agent-based architecture**, where a lightweight monitoring agent runs on each monitored system, collects system and container metrics, and sends them to a centralized backend.

The backend processes and stores monitoring data in **PostgreSQL**, broadcasts live updates through **Socket.IO**, and powers an interactive **React dashboard** for real-time visualization and monitoring.

> Syntra provides a practical foundation for building infrastructure monitoring and observability systems.

---

## 🎯 Problem Statement

Modern development and IT environments often involve multiple systems, services, and Docker containers running simultaneously. Monitoring these resources manually can make it difficult to identify performance issues, resource spikes, and system availability problems in real time.

Traditional monitoring approaches may also require checking multiple systems or tools separately, making centralized visibility and quick issue detection more challenging.

**Syntra addresses this problem by providing a centralized, real-time monitoring platform that collects host and Docker container metrics through lightweight monitoring agents and presents them through an interactive dashboard.**

The platform enables users to:

* Monitor CPU, memory, and system uptime
* Track Docker container performance
* Identify online and offline systems
* Detect threshold-based resource alerts
* View real-time and historical metrics
* Monitor multiple systems from a centralized dashboard

---

## 💡 Why Syntra?

Syntra was designed to explore how a distributed monitoring system can combine **agent-based metric collection, REST APIs, real-time communication, persistent storage, and an interactive frontend** into a single full-stack platform.

Instead of building only a dashboard or a standalone monitoring script, Syntra connects the complete workflow:

```text
System / Docker Containers
          ↓
   Monitoring Agent
          ↓
       REST API
          ↓
   Express Backend
          ↓
      PostgreSQL
          ↓
      Socket.IO
          ↓
    React Dashboard
```

This approach demonstrates practical implementation of:

* 🔹 Full-Stack Development
* 🔹 Distributed and Agent-Based Architecture
* 🔹 REST API Development
* 🔹 Real-Time Web Communication
* 🔹 Database Design and Persistence
* 🔹 Docker and Container Monitoring
* 🔹 Infrastructure Observability
* 🔹 Data Visualization

The goal of Syntra is to provide a practical and extensible foundation for understanding and implementing real-time infrastructure monitoring systems.

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

### 🚨 Threshold-Based Alerts

Syntra monitors resource usage and generates alerts when configured thresholds are exceeded.

* 🔴 High CPU Usage Alerts
* 🟠 High Memory Usage Alerts
* ⚙️ Threshold-Based Monitoring
* 🔄 Alert Resolution when conditions return to normal

---

### 📡 Real-Time Observability

Syntra uses **Socket.IO** to deliver live monitoring updates.

* ⚡ Real-Time Metric Updates
* 🔄 Live Dashboard Synchronization
* 📊 Continuous System Monitoring
* 🌐 Multi-System Monitoring

---

### 💾 Persistent Metrics Storage

Monitoring data is stored using **PostgreSQL**, allowing the platform to maintain historical infrastructure metrics.

This supports:

* Historical Metric Analysis
* Persistent Monitoring Records
* System Performance Tracking
* Future Analytics and Reporting

---

# 🏗️ System Architecture

```text
                         ┌─────────────────────┐
                         │   Monitored System  │
                         │                     │
                         │  Host + Docker      │
                         └──────────┬──────────┘
                                    │
                                    ▼
                         ┌─────────────────────┐
                         │  Monitoring Agent   │
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
                      │ • Metric Processing       │
                      │ • Alert Detection         │
                      │ • System Management       │
                      └─────────────┬─────────────┘
                                    │
                     ┌──────────────┴──────────────┐
                     │                             │
                     ▼                             ▼
           ┌──────────────────┐          ┌──────────────────┐
           │   PostgreSQL     │          │    Socket.IO     │
           │                  │          │                  │
           │ Persistent Data  │          │ Real-Time Events │
           └────────┬─────────┘          └────────┬─────────┘
                    │                             │
                    └──────────────┬──────────────┘
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

# 🔄 How Syntra Works

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

The monitoring agent collects system and Docker metrics using:

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

Monitoring metrics are persisted in **PostgreSQL** for historical monitoring and analysis.

---

### 5️⃣ Real-Time Communication

The backend broadcasts live monitoring events using:

```text
Socket.IO
```

This allows connected dashboards to receive updates without continuously polling the server.

---

### 6️⃣ Monitoring Dashboard

The React dashboard provides a centralized view of monitored infrastructure.

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

Make sure the following are installed:

* Node.js
* npm
* PostgreSQL
* Docker
* Docker Compose

Verify the installations:

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

Move into the project directory:

```bash
cd Syntra
```

---

# 🗄️ Backend Setup

Navigate to the backend:

```bash
cd backend
```

Install dependencies:

```bash
npm install
```

Create the environment file:

```bash
copy .env.example .env
```

Configure the required database connection inside `.env`.

Initialize the database using the provided:

```text
schema.sql
```

Start the backend:

```bash
npm run dev
```

---

# 🎨 Frontend Setup

Open a new terminal and navigate to:

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

Open another terminal and navigate to:

```bash
cd agent
```

Install dependencies:

```bash
npm install
```

Create the environment file:

```bash
copy .env.example .env
```

Configure the backend URL and monitoring-agent settings in `.env`.

Start the monitoring agent:

```bash
npm run dev
```

The agent will begin collecting system and Docker metrics and sending them to the backend.

> **Note:** The monitoring agent is designed to run separately on each system being monitored, while the backend and dashboard provide centralized monitoring.

---

# 🐳 Docker Deployment

Syntra includes Docker configuration for running the **core application services** in containers.

From the project root:

```bash
docker compose up --build
```

To run the services in detached mode:

```bash
docker compose up -d
```

To stop the services:

```bash
docker compose down
```

### Docker Architecture

Docker Compose starts the following core services:

```text
Docker Compose
│
├── PostgreSQL
├── Backend
└── Frontend
```

The **monitoring agent is not started by Docker Compose**. It is designed to run separately on each monitored machine so that it can collect that machine's host and Docker metrics.

> **Important:** The monitoring agent should be configured with the backend URL of the Syntra instance it needs to report metrics to.

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
| Threshold-Based Alerts      | ✅         |
| PostgreSQL Storage          | ✅         |

---

# 🔐 Environment Variables

Create `.env` files using the provided `.env.example` files.

Keep environment-specific credentials and configuration values outside the repository.

### Backend

Example:

```env
PORT=8000
DATABASE_URL=postgresql://postgres:postgres@localhost:5432/syntra
```

For the monitoring agent, configure the backend connection and system-specific settings according to `agent/.env.example`.

> ⚠️ **Never commit `.env` files, passwords, API keys, or other sensitive credentials to GitHub.**

---

# 🎯 Project Goals

Syntra was built to explore and implement practical concepts related to:

* Distributed Systems
* Observability
* Real-Time Systems
* Agent-Based Architecture
* REST APIs
* WebSockets
* Infrastructure Monitoring
* Docker Monitoring
* System Metrics Collection
* Data Visualization
* PostgreSQL
* Containerization

---

# ✅ Project Status

The core implementation of **Syntra is complete**.

The project successfully implements the planned monitoring workflow, including system metric collection, Docker monitoring, backend processing, persistent storage, real-time communication, alerts, and a centralized React dashboard.

### Implemented Capabilities

* [x] Host System Monitoring
* [x] CPU and Memory Monitoring
* [x] System Uptime Monitoring
* [x] Online / Offline Detection
* [x] Docker Container Monitoring
* [x] Container CPU and Memory Metrics
* [x] Real-Time Dashboard
* [x] Socket.IO Communication
* [x] PostgreSQL Storage
* [x] Historical Metrics
* [x] Threshold-Based Alerts
* [x] Multi-System Monitoring
* [x] REST API-Based Communication
* [x] Agent-Based Monitoring Architecture
* [x] Docker and Docker Compose Support
* [x] Interactive React Dashboard

> **Project Status:** Completed implementation for the current project scope.

---

# 🔮 Future Enhancements

Although the current implementation is complete, Syntra can be extended in the future to support larger-scale and production-oriented observability requirements.

Potential enhancements include:

* 🔐 **Authentication & Authorization** — secure access control for monitoring dashboards and APIs.
* 🔔 **Advanced Alert Notifications** — email, webhook, or other notification channels for critical alerts.
* 📊 **Advanced Analytics** — deeper metric analysis, performance trends, and customizable dashboards.
* ☁️ **Cloud Deployment** — deployment on cloud infrastructure for remote and centralized monitoring.
* ☸️ **Kubernetes Monitoring** — monitoring Kubernetes clusters, nodes, pods, and workloads.
* 📈 **Improved Scalability** — optimizing the platform for a larger number of monitored systems and higher metric volumes.
* 🧩 **Extended Infrastructure Monitoring** — support for additional infrastructure components and services.

These are **potential future enhancements**, not unfinished components of the current implementation.

---

# 💡 Future Vision

Syntra can evolve from host and Docker monitoring into a broader infrastructure observability platform:

```text
🖥️ Host Systems
        ↓
🐳 Docker Containers
        ↓
☸️ Kubernetes
        ↓
☁️ Cloud Infrastructure
        ↓
📊 Centralized Observability
```

The long-term vision is to provide a centralized platform capable of collecting, processing, analyzing, and visualizing infrastructure health and performance across different environments.

---

# 🤝 Contributing

Contributions, ideas, and improvements are welcome.

You can:

* Fork the repository
* Create a feature branch
* Make your changes
* Submit a pull request
* Open an issue

---

# 📄 License

This project is developed for educational, learning, experimentation, and portfolio purposes.

---

<div align="center">

## ⚡ Built with a focus on Real-Time Systems, Distributed Architecture & Observability

### ⭐ If you found this project interesting, consider giving it a star!

<br/>

### 👨‍💻 Developed by Sujal Singh

**B.Tech Hons — CSE with AI & Analytics**

🔗 GitHub: [SujalSingh9252](https://github.com/SujalSingh9252)

---

**Syntra — Monitor. Observe. Analyze. React. ⚡**

</div>




