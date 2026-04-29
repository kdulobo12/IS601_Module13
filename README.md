## 📦 Module 13: JWT Authentication + Frontend + Playwright + CI/CD

## 📌 Project Overview
This project implements a secure authentication system using JWT (JSON Web Tokens) with a FastAPI backend and PostgreSQL database.
Users can:
Register a new account
Log in using valid credentials
Receive a JWT token for authentication
In addition, this project includes:
Front-end login and registration pages
Playwright end-to-end (E2E) tests
Docker containerization
GitHub Actions CI/CD pipeline for automated testing and deployment

## 🧩 Features Implemented

## 🔐 Authentication (Backend)
/register → Creates a new user
/login → Authenticates user and returns JWT
Passwords are securely hashed before storing
Duplicate users are prevented
Pydantic validation ensures correct input format

## 🌐 Front-End
register.html
Email + password input
Confirm password check
Client-side validation (email format, password length)
login.html
Email + password input
Displays success/error messages
Stores JWT token in localStorage

## 🎭 Playwright Testing
Positive tests:
Successful registration
Successful login
Negative tests:
Short password → error
Wrong credentials → error

## 🐳 DevOps (CI/CD)
Docker used for containerization
GitHub Actions pipeline:
Spins up database + backend
Runs tests automatically
Builds Docker image
Pushes to Docker Hub

## 🛠️ Tech Stack
Python (FastAPI)
PostgreSQL
SQLAlchemy
Pydantic
JWT Authentication
HTML / CSS / JavaScript
Playwright
Docker
GitHub Actions

## 🚀 Setup Instructions
🧩 1. Clone Repository

## 🧩 2. Create Virtual Environment
python3 -m venv venv
source venv/bin/activate   # Mac
venv\Scripts\activate      # Windows

## 🧩 3. Install Dependencies
pip install -r requirements.txt

## 🧩 4. Run Backend
uvicorn app.main:app --reload
Open:
http://localhost:8000
API Docs:
http://localhost:8000/docs

## 🧩 5. Run Front-End
cd frontend
python3 -m http.server 5500
Open in browser:
http://localhost:5500/register.html
http://localhost:5500/login.html

## 🧩 6. JWT Authentication Usage
Register
POST /register
{
  "email": "test@example.com",
  "password": "password123"
}
Login
POST /login
Response:
{
  "access_token": "your_jwt_token",
  "token_type": "bearer"
}
👉 Token is stored in browser localStorage

## 🧪 Testing
Backend Tests
pytest
Playwright Setup
npm install
npx playwright install
Run Playwright Tests
npx playwright test

## 🐳 Docker Setup
Run with Docker
docker compose up --build
Build Image
docker build -t module14-app .
Run Container
docker run -p 8000:8000 module14-app

## 🔄 CI/CD Pipeline
GitHub Actions automatically:
Starts PostgreSQL + FastAPI
Runs pytest
Runs Playwright tests
Builds Docker image
Pushes to Docker Hub

## 🐳 Docker Hub Repository :
https://hub.docker.com/repository/docker/kdulobo12/module13-web/general

👉 Docker Image Link: https://hub.docker.com/r/kdulobo12/is601module13

## 📸 Screenshots

✅ GitHub Actions Success image

<img width="3344" height="1612" alt="image" src="https://github.com/user-attachments/assets/82b0a1ea-10f1-41ea-aa72-3024d2ba4925" />

✅ Playwright tests passing


✅ Register page working
<img width="1680" height="1050" alt="Screenshot 2026-04-28 at 19 32 08" src="https://github.com/user-attachments/assets/4defe146-2184-4e40-851a-ee1d908c2141" />

✅ Login page working
<img width="1680" height="1050" alt="Screenshot 2026-04-28 at 19 32 01" src="https://github.com/user-attachments/assets/ae1f121b-6b1e-442c-a166-924198465c1d" />


## 💡 Reflection (Short Summary)

This project helped me understand how authentication works in a real application. I implemented JWT-based login and registration, where passwords are hashed before storing them in the database. I also built front-end pages and connected them to the backend API.
Writing Playwright tests helped me test the application from a user perspective, including both successful and failed cases. Setting up Docker and GitHub Actions showed how CI/CD pipelines automate testing and deployment.
Overall, this project improved my understanding of full-stack development, security practices, and DevOps workflows.

## 🔥 Quick Commands Cheat Sheet

Action	Command
Run backend	uvicorn app.main:app --reload
Run frontend	python3 -m http.server 5500
Run pytest	pytest
Run Playwright	npx playwright test
Docker run	docker compose up --build
Push code	git add . && git commit -m "msg" && git push

## 👩‍💻 Author
Krupa Dulobo
