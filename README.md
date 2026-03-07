# ACEest Fitness & Gym – DevOps CI/CD Pipeline

## Project Overview

This project demonstrates the implementation of a **modern DevOps workflow** for the ACEest Fitness & Gym web application. The objective is to automate the software lifecycle from development to build validation using industry-standard tools including **Git, Docker, Jenkins, Pytest, and GitHub Actions**.

The application is a simple **Flask-based web service** designed to simulate a lightweight fitness and gym management system.

This project showcases how **Continuous Integration and Continuous Delivery (CI/CD)** pipelines help ensure:

* Code quality
* Automated testing
* Consistent deployment environments
* Faster delivery cycles

---

# Technology Stack

| Tool           | Purpose                      |
| -------------- | ---------------------------- |
| Python (Flask) | Web Application              |
| Git & GitHub   | Version Control              |
| Pytest         | Unit Testing Framework       |
| Docker         | Application Containerization |
| Jenkins        | Build Automation             |
| GitHub Actions | CI/CD Pipeline Automation    |

---

# Project Structure

```
aceest-devops/
│
├── app.py
├── requirements.txt
├── Dockerfile
│
├── tests/
│   └── test_app.py
│
├── .github/
│   └── workflows/
│        └── main.yml
│
└── README.md
```

---

# Flask Application

The Flask application provides a simple endpoint to simulate a fitness service backend.

Example endpoint:

```
GET /
```

Response:

```
Welcome to ACEest Fitness & Gym
```

---

# Local Setup Instructions

### 1. Clone the Repository

```
git clone https://github.com/<your-username>/aceest-devops.git
cd aceest-devops
```

### 2. Create Virtual Environment

```
python -m venv venv
```

Activate the environment:

Windows:

```
venv\Scripts\activate
```

Linux/Mac:

```
source venv/bin/activate
```

### 3. Install Dependencies

```
pip install -r requirements.txt
```

### 4. Run the Application

```
python app.py
```

Application runs on:

```
http://localhost:5000
```

---

# Running Unit Tests

Unit testing is implemented using **Pytest** to verify application functionality.

Run tests using:

```
pytest
```

Expected output:

```
tests/test_app.py .... PASSED
```

Testing ensures the core endpoints behave correctly before the code proceeds to the build pipeline.

---

# Docker Containerization

The application is containerized using **Docker** to ensure consistent environments across development and build stages.

### Build Docker Image

```
docker build -t aceest-app .
```

### Run Docker Container

```
docker run -p 5000:5000 aceest-app
```

Access application:

```
http://localhost:5000
```

Docker guarantees that the application runs the same way across all environments.

---

# Jenkins Build Integration

Jenkins is used as a **secondary validation layer** for the CI pipeline.

### Jenkins Workflow

1. Jenkins pulls the latest code from GitHub.
2. Jenkins builds the project environment.
3. Jenkins performs Docker build validation.

### Jenkins Build Steps

```
git clone repository
docker build -t aceest-app .
```

This confirms that the application successfully builds in an isolated CI environment.

---

# GitHub Actions CI/CD Pipeline

The project includes an automated CI/CD pipeline defined in:

```
.github/workflows/main.yml
```

### Pipeline Trigger

The pipeline runs automatically on:

* Every **push**
* Every **pull request**

### Pipeline Stages

#### 1. Build & Lint

The workflow installs dependencies and validates Python syntax.

#### 2. Docker Image Build

The pipeline builds the Docker container to verify the containerization process.

#### 3. Automated Testing

Pytest is executed inside the pipeline to ensure application stability.

### Example Workflow

```
Build → Docker Build → Run Tests
```

If all stages pass successfully, the build is considered stable.

---

# CI/CD Workflow Diagram

```
Developer Push Code
        ↓
GitHub Repository
        ↓
GitHub Actions Pipeline
   (Build + Test + Docker)
        ↓
Jenkins Build Validation
        ↓
Successful CI Pipeline
```

---

# DevOps Best Practices Implemented

* Version-controlled infrastructure
* Automated testing
* Containerized application environment
* Continuous Integration
* Build automation
* Reproducible builds

---

# Conclusion

This project demonstrates a practical implementation of **DevOps CI/CD principles** using modern tools.

By integrating **GitHub Actions, Docker, Jenkins, and automated testing**, the system ensures:

* Code reliability
* Faster development cycles
* Consistent deployment environments
* Automated build verification

This workflow reflects real-world DevOps practices used in modern software engineering teams.

---

# Author

**Amitosh Gautam**
M.Tech –  Introduction to DEVOPS Assignment 1
ACEest Fitness & Gym CI/CD Implementation
