# 3-Tier Demo Application (Frontend · Backend · Database)

This repository represents the **system-level orchestration** of a 3-tier web application using **Docker Compose**.

> ⚠️ **Important**: This repository does **not** contain application source code directly. Each tier (frontend, backend, database) lives in its **own independent GitHub repository** and is linked here conceptually and operationally via Docker images.

---

## 🧱 Architecture Overview

This project follows a **classic 3-tier architecture**:

1. **Frontend (Presentation Layer)**

   * React application
   * Handles UI and user interactions
   * Communicates with the backend via HTTP APIs

2. **Backend (Application Layer)**

   * Node.js + Express server
   * Exposes REST APIs
   * Handles business logic
   * Communicates with MongoDB

3. **Database (Data Layer)**

   * MongoDB
   * Stores persistent application data

All three tiers run in **separate Docker containers** and communicate over a **shared Docker network**.

---

## 📦 Related Repositories (Source Code)

Each tier is developed, versioned, and maintained independently:

* **Frontend**: [https://github.com/preranabl/Demo-frontend](https://github.com/preranabl/Demo-frontend)
* **Backend**: [https://github.com/preranabl/Demo-backend](https://github.com/preranabl/Demo-backend)
* **Database**: [https://github.com/preranabl/Demo-database](https://github.com/preranabl/Demo-database)

This repository only orchestrates these services using Docker Compose.

---

## 🐳 Docker-Based Deployment Model

Instead of cloning all repositories locally, this setup uses **Docker Hub images**:

* `preranablownlama/demo-frontend`
* `preranablownlama/demo-backend`
* `preranablownlama/demo-db`

Docker Compose pulls these images and runs them together as one system.

---

## 🔁 Request Flow (End-to-End)

1. User opens the **frontend** in the browser
2. Frontend sends an HTTP request to the **backend API**
3. Backend processes the request
4. Backend queries or updates **MongoDB**
5. Database returns data to backend
6. Backend sends response back to frontend
7. Frontend updates the UI

```
Browser → Frontend → Backend → MongoDB
                      ←
```

---

## ⚙️ docker-compose.yml Responsibilities

The `docker-compose.yml` file:

* Starts all 3 services
* Creates a shared Docker network
* Defines service-to-service communication
* Injects environment variables
* Manages database persistence using volumes

This file is the **single entry point** to run the entire system.

---

## 🚀 How to Run the Application

```bash
docker-compose up
```

### Access Points

* Frontend: [http://localhost:3001](http://localhost:3001)
* Backend API: [http://localhost:3000](http://localhost:3000)
* MongoDB: mongodb://localhost:27017

---

## 🧠 Why This Design?

✔ Clear separation of concerns
✔ Independent development & deployment
✔ Scales well in real-world systems
✔ Matches industry microservice practices
✔ Easy migration to Kubernetes / Cloud

---

## 📌 Notes for Reviewers / Interviewers

* Each tier has its own Git repository and Docker image
* This repository is an **infrastructure orchestration layer**
* No code duplication or tight coupling between services

---

## 👤 Author

**Prerana Blown Lama**

3-Tier Application · Doc
