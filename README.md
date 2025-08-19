# 🌴 Dream Vacation App — Dockerized Full-Stack Project with CI/CD

This project containerizes a full-stack web application using **Docker**, **Docker Compose**, and integrates **CI/CD pipelines** via **GitHub Actions**.

---

## 🧩 Tech Stack

- **Frontend**: React + Nginx
- **Backend**: Node.js + Express
- **Database**: PostgreSQL
- **Containerization**: Docker & Docker Compose
- **CI/CD**: GitHub Actions

---

## 🛠️ What Was Done

- Created `Dockerfile` for:
  - Frontend (React + Nginx)
  - Backend (Node.js + Express)
- Created `docker-compose.yml` to orchestrate services
- Added `.env` for managing environment variables
- Configured `.gitignore` to exclude `.env` and `node_modules`
- Implemented CI/CD workflows:
  - `.github/workflows/frontend.yml`
  - `.github/workflows/backend.yml`

---

## ⚙️ CI/CD Workflow Overview

CI/CD is powered by **GitHub Actions**, automating build and deployment to Docker Hub on every push to the `dev` branch.

### 🔧 Frontend Workflow (`Dream-Frontend CI/CD`)

**Trigger**: Push to `dev` branch with changes in `frontend/` directory.

**Steps**:

1. Checkout code using `actions/checkout@v3`
2. Set up Node.js (v18) using `actions/setup-node@v4`
3. Install dependencies with `npm install`
4. *(Optional)* Run ESLint for code quality
5. Login to Docker Hub using `docker/login-action@v3` and GitHub secrets
6. Set up Docker Buildx using `docker/setup-buildx-action@v3`
7. Build and push Docker image using `docker/build-push-action@v6`
   - Tag: `${{ secrets.DOCKER_USERNAME }}/dream-frontend:${{ github.sha }}`
   - Context: `frontend/`
   - Dockerfile: `frontend/Dockerfile`

### 🔧 Backend Workflow (`Dream-Backend CI/CD`)

**Trigger**: Push to `dev` branch with changes in `backend/` directory.

**Steps**:

1. Checkout code using `actions/checkout@v3`
2. Set up Node.js (v18) using `actions/setup-node@v4`
3. Install dependencies with `npm install`
4. *(Optional)* Run ESLint for code quality
5. Login to Docker Hub using `docker/login-action@v3` and GitHub secrets
6. Set up Docker Buildx using `docker/setup-buildx-action@v3`
7. Build and push Docker image using `docker/build-push-action@v6`
   - Tag: `${{ secrets.DOCKER_USERNAME }}/dream-backend:${{ github.sha }}`
   - Context: `backend/`
   - Dockerfile: `backend/Dockerfile`

---

## 📦 Docker Workflow

### 🔨 Build Images Locally

```bash
docker build -t incrediblenoble08/dream-vacation-frontend ./frontend
docker build -t incrediblenoble08/dream-vacation-backend ./backend

## 🚀 Push to Docker Hub

docker push incrediblenoble08/dream-vacation-frontend
docker push incrediblenoble08/dream-vacation-backend

## ▶️ Start Services
docker-compose up -d

## Dream-Vacation-App/
│
├── frontend/               # React app
│   └── Dockerfile          # Multi-stage build with Nginx
│
├── backend/                # Node.js + Express API
│   └── Dockerfile          # Runs on Node 16/18
│
├── .env                    # Environment variables (excluded from Git)
├── .gitignore              # Ignores .env and node_modules
├── docker-compose.yml      # Orchestrates services
├── .github/
│   └── workflows/
│       ├── frontend.yml    # CI/CD for frontend
│       └── backend.yml     # CI/CD for backend
└── README.md

## 🚀 Usage
1. Clone the Repository
git clone https://github.com/your-username/Dream-Vacation-App.git
cd Dream-Vacation-App

2. Create a .env File
POSTGRES_DB=
POSTGRES_USER=
POSTGRES_PASSWORD=
DB_HOST=
DB_PORT=
PORT=

3. Start the Application
docker-compose up --build

4. Access Services
Frontend: http://localhost:3000

Backend: http://localhost:5000

PostgreSQL: localhost:5432


📤 Docker Hub Images
Frontend: docker.io/incrediblenoble08/dream-vacation-frontend

Backend: docker.io/incrediblenoble08/dream-vacation-backend

✅ Features
⚙️ Multi-stage builds for optimized frontend

🧩 Modular architecture with separate services

🔐 Secure environment configuration via .env

💾 PostgreSQL data persistence with Docker volumes

🚀 Automated CI/CD pipelines for seamless deployment
