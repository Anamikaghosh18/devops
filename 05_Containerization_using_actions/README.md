# Containerizing a Python App with Docker & GitHub Actions

This project demonstrates how to **containerize a Python application using Docker** and automate the workflow using **GitHub Actions (CI pipeline)**.

It is a **simple demo project** to showcase CI/CD basics with Docker.

**🔗 repo link:**
`https://github.com/Anamikaghosh18/containerization-using-actions`


## Project Structure

```
container-using-actions/
├── app.py
├── requirements.txt
├── Dockerfile
└── .github/
    └── workflows/
        └── c1.yml
```

## 🔄 CI Workflow (GitHub Actions)

The pipeline is triggered on:

* ✅ Push to `main` branch
* ✅ Pull requests

### ⚙️ Workflow Steps

1. Checkout repository
2. Set up Python environment
3. Install dependencies
4. Run Python application
5. Build Docker image
6. Push Docker image to Docker Hub

## 🐳 Dockerization

The application is containerized using Docker.

### 🧱 Configuration

* **Base Image:** Python 3.9-slim
* **Dependency Management:** `requirements.txt`
* **Execution:** `app.py` inside container


