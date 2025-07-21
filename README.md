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
<img width="1600" height="900" alt="Screenshot (398)" src="https://github.com/user-attachments/assets/17f7fd18-943b-4e5f-9602-b8918c503de2" />

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
<img width="635" height="365" alt="Screenshot (387)" src="https://github.com/user-attachments/assets/132106eb-92dd-43a5-ab8e-1ef32f6244e1" />

**👀 Terminal & Frontend Screenshots**
<img width="1600" height="843" alt="Screenshot (383)" src="https://github.com/user-attachments/assets/159b9ced-f5be-444b-bbca-5a44b230d5a1" />
<img width="1600" height="864" alt="Screenshot (384)" src="https://github.com/user-attachments/assets/fdb6790b-a4d4-4fc8-b6b9-c0778b260b90" />
<img width="1600" height="855" alt="Screenshot (392)" src="https://github.com/user-attachments/assets/46fc1e15-5ef3-4607-b723-4a3ac5dbe75d" />
<img width="1600" height="845" alt="Screenshot (395)" src="https://github.com/user-attachments/assets/52e426a0-9ee4-4725-84d6-1143f1d06b7e" />
<img width="1600" height="861" alt="Screenshot (396)" src="https://github.com/user-attachments/assets/fe02af80-ac72-45c5-b24f-a73e97ebd8a9" />

**📁 Project Structure**
Dream-Vacation-App/
│
├── frontend/           # React app
│   └── Dockerfile      # Multi-stage build with Nginx
│
├── backend/            # Node.js + Express API
│   └── Dockerfile      # Runs on Node 16/18
│
├── .env                # Environment variables (NOT pushed to GitHub)
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
Frontend: docker.io/your-username/dream-vacation-frontend

Backend: docker.io/your-username/dream-vacation-backend

**✅ Features**
⚙️ Multi-stage builds for optimized frontend

🧩 Modular architecture with separate services

🔐 Secure environment configuration via .env

💾 PostgreSQL data persistence with Docker volumes

📦 Ready for local and production deployment

