# 🌴 Dream Vacation App — Dockerized Full-Stack Project

This project focuses on containerizing a full-stack web application using **Docker** and **Docker Compose**. The application comprises:

- 🌐 **React frontend**
- ⚙️ **Node.js backend**
- 🗄️ **PostgreSQL database**

---

## 🛠️ What Was Done

- Existing code for frontend and backend was provided
- Created `Dockerfile` for:
  - Frontend (React with Nginx)
  - Backend (Node.js with Express)
- Created `docker-compose.yml` to orchestrate services
- Added `.env` file for managing environment variables
- Added `.gitignore` to exclude `.env` and `node_modules`
- Created repositories:
  - [`dream-vacation-frontend`](#)
  - [`dream-vacation-backend`](#)

---

## 📦 Docker Workflow

1. **Build Images:**
   ```bash
   docker build -t incrediblenoble08/dream-vacation-frontend ./frontend
   docker build -t incrediblenoble08/dream-vacation-backend ./backend

2. **Push Images to Docker Hub:**
    docker push aiyus/dream-vacation-frontend
    docker push aiyus/dream-vacation-backend


3. **Start Services:**
    docker-compose up -d

**👀 Terminal & Frontend Screenshots**

**📁 Project Structure**
Dream-Vacation-App/
├── frontend/           # React app
│   └── Dockerfile      # Multi-stage build with Nginx
├── backend/            # Node.js + Express API
│   └── Dockerfile      # Runs on Node 16/18
├── .env                # Environment variables (NOT pushed)
├── .gitignore          # Ignores .env and node_modules
├── docker-compose.yml  # Orchestrates services
└── README.md


**🚀 Usage**

**1. Clone the repository:**

git clone https://github.com/your-username/Dream-Vacation-App.git
cd Dream-Vacation-App

**2. Create a .env file:**
POSTGRES_DB=vacation_db
POSTGRES_USER=postgres
POSTGRES_PASSWORD=secret123
DB_HOST=db
DB_PORT=5432
PORT=5000

**3. Start the application:**
docker-compose up --build

**4. Access services:**
Frontend: http://localhost:3000

Backend: http://localhost:5000

PostgreSQL: localhost:5432

**📤 Pushed Docker Images**

Frontend: docker.io/incrediblenoble08/dream-vacation-frontend

Backend: docker.io/incrediblenoble08/dream-vacation-backend

**✅ Features**
⚙️ Multi-stage builds for optimized frontend

🧩 Modular architecture with separate services

🔐 Secure environment configuration via .env

💾 PostgreSQL data persistence with Docker volumes

📦 Ready for local and production deployment

