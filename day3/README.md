This project demonstrates how to **containerize a Python application using Docker** and automate the workflow using **GitHub Actions (CI pipeline)**.

## 📂 Project Structure

```
container-using-actions/
├── app.py
├── requirements.txt
├── Dockerfile
└── .github/
    └── workflows/
        └── c1.yml
```

---

## 🔄 CI Workflow

The pipeline is triggered on:

* Push to `main` branch
* Pull requests

### Workflow Steps:

1. Checkout repository
2. Setup Python environment
3. Install dependencies
4. Run tests (pytest)
5. Build Docker image


## 🐳 Dockerization

The application is containerized using Docker:

* Base image: Python 3.10
* Dependencies installed via `requirements.txt`
* Application runs inside isolated container

### Build Image:

```
docker build -t my-python-app .
```

### Run Container:

```
docker run -p 5000:5000 my-python-app
```
