---

# 🚀 Dockerized Microservices App

A simple **microservices-based application** built with **React, Node.js, Postgres, Redis, and Nginx**, all orchestrated with **Docker Compose**.  

This project demonstrates how to structure, containerize, and run a full-stack app with background jobs, caching, and reverse proxying.

---

## ✨ Features

- 📦 **Microservices architecture** – modular and scalable.
- ⚡ **React frontend** – modern UI for users.
- 🔗 **Node.js API** – REST backend with Express.
- 🗄️ **Postgres database** – reliable relational storage.
- 🧠 **Redis** – fast cache + job queue.
- 🔄 **Worker service** – background job processing.
- 🌐 **Nginx reverse proxy** – routes requests between frontend and backend.

---

## 📂 Project Structure

```

.
├── client/     # React frontend
├── server/     # API backend
├── worker/     # Background worker
├── nginx/      # Nginx config
└── docker-compose.yml

```

---

## 🏗️ Architecture

```

Browser ([http://localhost:3000](http://localhost:3000))
│
▼
Nginx (reverse proxy)
├── /api → API (server)
│        ├── Postgres (database)
│        └── Redis (cache / queue)
└── /    → Client (React frontend)

Worker (background jobs)
└── Redis (for queue / pub-sub)

````

---

## ⚙️ Getting Started

### ✅ Prerequisites
- [Docker](https://docs.docker.com/get-docker/)  
- [Docker Compose](https://docs.docker.com/compose/)

### 1. Clone the repo
```bash
git clone git@github.com:EslamNasser0/Microservices-Docker-React.git
cd Microservices-Docker-React
````

### 2. Run with Docker Compose

```bash
docker compose up --build
```

### 3. Access the app

* Client: [http://localhost:3000](http://localhost:3000)
* API: routed internally through `/api`
* React dev server (optional): [http://localhost:3000](http://localhost:3000)

---

## 🧩 Environment Variables

Key variables (set in `docker-compose.yml`):

**Postgres**

* `POSTGRES_PASSWORD=postgres_password`

**API**

* `PGUSER=postgres`
* `PGPASSWORD=postgres_password`
* `PGHOST=postgres`
* `PGDATABASE=postgres`
* `PGPORT=5432`
* `REDIS_HOST=redis`
* `REDIS_PORT=6379`

**Worker**

* `REDIS_HOST=redis`
* `REDIS_PORT=6379`
