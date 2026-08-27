# 🏗️ Book Shop — Backend Platform

> Backend infrastructure and platform components for the **Book Shop Microservices Architecture**.

---

## 👨‍🎓 Student Information

| Field              | Details             |
| :----------------- | :------------------ |
| **Student Name**   | **Ashen Indeewara** |
| **Student Number** | **241722049**       |
| **GCP Project ID** | **bookstore-ashen** |

---

## 📖 Project Overview

The **Bookstore Backend Platform** repository contains the core infrastructure components required to run and connect the Book Shop microservices.

Instead of placing all backend functionality into a single application, the system uses a **microservices architecture** with centralized configuration, service discovery, and an API Gateway.

This repository acts as the platform layer between the frontend and the individual backend services.

---

## 🧩 Platform Components

### 🌐 API Gateway

The API Gateway provides a centralized entry point for requests coming from the frontend application.

Responsibilities include:

* Routing client requests
* Forwarding requests to the appropriate microservice
* Providing a single backend entry point
* Supporting communication between frontend and backend services

### ⚙️ Config Server

The Config Server provides centralized configuration management for the microservices environment.

It allows services to retrieve their configuration from a centralized location.

### 🔎 Eureka Server

The Eureka Server provides **service discovery** for the microservices architecture.

Services can register themselves with Eureka and discover other services dynamically.

---

## 🏗️ Architecture

```text
                 ┌──────────────────────────┐
                 │    Book Shop Frontend    │
                 │     React + Vite         │
                 └────────────┬─────────────┘
                              │
                              ▼
                 ┌──────────────────────────┐
                 │       API Gateway        │
                 └────────────┬─────────────┘
                              │
             ┌────────────────┼────────────────┐
             │                │                │
             ▼                ▼                ▼
      ┌─────────────┐  ┌─────────────┐  ┌─────────────┐
      │    User     │  │    Book     │  │    Order    │
      │   Service   │  │   Service   │  │   Service   │
      └─────────────┘  └─────────────┘  └─────────────┘
             │                │                │
             └────────────────┼────────────────┘
                              │
                              ▼
                    ┌──────────────────┐
                    │  Eureka Server   │
                    │ Service Discovery│
                    └──────────────────┘

                    ┌──────────────────┐
                    │  Config Server   │
                    │   Central Config │
                    └──────────────────┘
```

---

## 📂 Repository Structure

```text
bookstore-backend-platform/
│
├── .github/
│   └── workflows/
│
├── api-gateway/
│
├── config-server/
│
├── eureka-server/
│
├── deploy/
│   └── startup-scripts/
│
├── .gitmodules
└── README.md
```

The repository currently contains the API Gateway, Config Server, Eureka Server, and deployment/startup scripts.

---

## 🚀 Getting Started

### Prerequisites

Make sure you have:

* Java Development Kit (JDK)
* Maven
* Git
* Access to the Book Shop backend services
* Required environment/configuration files

### Clone the Repository

```bash
git clone https://github.com/AshenIndeewara/bookstore-backend-platform.git
cd bookstore-backend-platform
```

### Initialize Submodules

The platform repository contains platform components managed as Git submodules.

```bash
git submodule update --init --recursive
```

### Start the Platform

Start the infrastructure components in the required order:

```text
1. Config Server
2. Eureka Server
3. API Gateway
```

Then start the individual backend services.

> The exact startup commands depend on the Maven configuration and deployment environment used for the project.

---

## 🔄 Request Flow

A typical request follows this flow:

```text
Frontend
   │
   ▼
API Gateway
   │
   ▼
Eureka Service Discovery
   │
   ▼
Target Microservice
   │
   ▼
Response
   │
   ▼
Frontend
```

---

## ☁️ Deployment

The repository includes deployment and startup scripts under:

```text
deploy/startup-scripts/
```

These scripts are intended to help automate the startup and deployment of the backend platform components.

---

## 🔐 Security

* Do not commit passwords or credentials.
* Do not commit private API keys.
* Keep environment-specific configuration outside the source code when appropriate.
* Protect cloud infrastructure credentials.
* Use secure configuration for production deployments.

---

## 🔗 Related Repositories

### Frontend

https://github.com/AshenIndeewara/bookstore-frontend

### Backend Platform

https://github.com/AshenIndeewara/bookstore-backend-platform

### Backend Services

https://github.com/AshenIndeewara/bookstore-backend-services

---

## 📌 Repository Role

This repository contains the **Platform / Infrastructure Layer** of the Book Shop Microservices Architecture.

It provides:

* API Gateway
* Centralized Configuration
* Service Discovery
* Deployment and Startup Support

---

## 👨‍💻 Author

**Ashen Indeewara**

**Student Number:** 241722049

**GCP Project:** `bookstore-ashen`
