# 🔐 authEncryption

**authEncryption** is a full-stack, microservices-based application demonstrating secure user authentication, tokenization, and encryption.  
It’s built using **Node.js**, **Express**, **Prisma**, **PostgreSQL**, and **React (Vite)** — following modern architectural principles and production-ready practices.

The project is structured into three independent services:
- **auth-service/** → Handles authentication, password hashing (bcrypt), and JWT token generation.  
- **customer-service/** → Manages customer CRUD operations through protected routes.  
- **frontend/** → React + Vite single-page application for users to register, log in, and manage customer data.

---

## 🧱 Architecture Overview

| Component | Description | Tech Stack |
|------------|--------------|-------------|
| **auth-service/** | Provides secure registration, login, and authentication APIs using bcrypt and JWT | Node.js, Express, Prisma, PostgreSQL |
| **customer-service/** | Handles CRUD operations for customer records with access restricted via JWT validation | Node.js, Express, Prisma, PostgreSQL |
| **frontend/** | React + Vite SPA that integrates both services with protected routes and API calls | React, Vite, Axios |

All services communicate independently and can be deployed separately, connected through a shared PostgreSQL database.

---

## 🧠 Core Concepts

### 🔹 Authentication Flow
1. **User Registration** → User submits email & password to `auth-service/register`.  
2. **Password Encryption** → Passwords are hashed using **bcrypt** before being stored.  
3. **Login** → Credentials verified via `auth-service/login`.  
4. **JWT Token Issuance** → Upon successful login, a **JWT token** is generated and returned to the frontend.  
5. **Protected Routes** → `customer-service` verifies JWT before allowing CRUD operations.

### 🔹 Encryption & Security
- **bcrypt** → For secure one-way password hashing.  
- **JWT** → For stateless session management and route protection.  
- **Environment Variables** → Database credentials and JWT secrets are stored securely in `.env` files.  
- **Input Validation** → API inputs are validated before database interaction.  

---

## 🌍 Future Improvements & Deployment

In future versions, the goal is to:
- ✅ Containerize the full stack using **Docker Compose** for one-command deployment.  
- ☁️ Deploy all services to **Google Cloud Run** or **AWS ECS** for scalability.  
- 🔐 Integrate **OAuth2** or **Google Sign-In** for seamless authentication.  
- 🧑‍💻 Add **Role-Based Access Control (RBAC)** for advanced authorization logic.  
- 📊 Implement **monitoring and logging** using Prometheus or Grafana.  

These steps will move `authEncryption` toward a production-ready, cloud-native application architecture.

---

## ⚙️ Prerequisites

Make sure you have the following installed:
- [Node.js](https://nodejs.org/) ≥ 18  
- [npm](https://www.npmjs.com/) ≥ 9 (or Yarn)  
- [PostgreSQL](https://www.postgresql.org/) (local or managed instance)  
- [Git](https://git-scm.com/)

---

## 🛠️ Setup Instructions

### 1️⃣ Clone the repository
```bash
git clone https://github.com/JeevanJyot55/authEncryption.git
cd authEncryption
