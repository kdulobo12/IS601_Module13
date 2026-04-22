
This project extends a FastAPI-based calculator application by implementing a Calculation model using SQLAlchemy, robust validation using Pydantic schemas, and a complete

CI/CD pipeline.

The application integrates PostgreSQL for persistence, uses a factory pattern for calculation logic, and includes unit and integration tests. Docker is used for containerization, and GitHub Actions automates testing and deployment to Docker Hub.

This module focuses on backend modeling, validation, and CI/CD automation.

⚙️ Features

FastAPI calculator backend
SQLAlchemy Calculation model
Pydantic schema validation
Factory pattern for operations (Add, Subtract, Multiply, Divide)
PostgreSQL database integration
Unit and integration testing
Dockerized application
GitHub Actions CI/CD pipeline
Docker Hub image deployment
🧮 Calculation Model

The Calculation model includes:

id (Primary Key)
a (First operand)
b (Second operand)
type (Operation type: Add, Sub, Multiply, Divide)
result (Optional stored result)
🧠 Factory Pattern

A factory pattern is used to handle different calculation types:

Add
Subtract
Multiply
Divide
This improves scalability and keeps logic clean and modular.

🔐 Validation (Pydantic)

CalculationCreate

Accepts: a, b, type
Validates:
Operation type must be valid
Division by zero is prevented
CalculationRead

Returns:
id, a, b, type, result
📦 Project Structure

. ├── app/ │ ├── models/ │ │ └── calculation.py │ ├── schemas/ │ │ └── calculation.py │ ├── operations/ │ │ └── factory.py │ ├── database.py │ └── main.py ├── tests/ │ ├── unit/ │ ├── integration/ │ └── e2e/ ├── docker-compose.yml ├── Dockerfile ├── requirements.txt ├── README.md └── Reflection.md

🧪 Testing

Test Types

Unit Tests

Validate each operation type
Test factory pattern logic
Test schema validation
Integration Tests

Database insertions
Data correctness verification
Error handling (invalid inputs)
📊 Coverage

High test coverage across models and validation
Tests run automatically in CI pipeline
🐳 Running the Project Locally

Step 1: Clone Repo

git clone https://github.com/kdulobo12/IS601_Module11 cd IS601_Module11 Step 2: Setup Virtual Environment python3 -m venv venv source venv/bin/activate pip install -r requirements.txt Step 3: Run with Docker docker compose down -v docker compose up --build Step 4: Access Application FastAPI App → http://localhost:8000 Swagger Docs → http://localhost:8000/docs pgAdmin → http://localhost:5050

🧪 Run Tests

pytest With coverage: pytest --cov=app --cov-report=html Open: htmlcov/index.html

🔄 CI/CD Pipeline

GitHub Actions workflow performs: Install dependencies Run unit + integration tests Build Docker image Run security scan (Trivy) Push image to Docker Hub

🐳 Docker Hub Repository

👉 Docker Image Link: https://hub.docker.com/r/kdulobo12/is601_module11

📸 Screenshots

✅ GitHub Actions Success image

✅ Docker Hub Image alt text

Link: https://hub.docker.com/r/kdulobo12/is601_module11

