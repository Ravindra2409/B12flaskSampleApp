# 🚀 CI/CD Automation for Python Web Application

This repository demonstrates two CI/CD pipelines for a simple Python web application using:

- **Jenkins Pipeline** for automated build, test, and deployment
- **GitHub Actions Workflow** for staging and production deployment

---

## 📦 Application Overview

The application is a basic Flask-based Python web app. It includes:

- `app.py`: Main application file
- `requirements.txt`: Dependency list
- `tests/`: Unit tests using `pytest`

---

## 🧪 Jenkins Pipeline Setup

### 🔧 Prerequisites

- Jenkins installed on a VM or cloud instance
- Python 3 and pip installed on the Jenkins server
- GitHub repository forked and cloned into Jenkins workspace

### 📁 Jenkinsfile

The `Jenkinsfile` defines a pipeline with the following stages:

1. **Build**: Create virtual environment and install dependencies
2. **Test**: Run unit tests using `pytest`
3. **Deploy**: Deploy to staging if tests pass
4. **Notifications**: Email alerts on success or failure

### 🔁 GitHub Trigger

- GitHub webhook configured to trigger Jenkins on push to `main`
- Webhook URL: `http://35.182.9.255:8080/github-webhook/`

### 📧 Email Notifications

- Configured in `Jenkinsfile` using `mail` step
- Alerts sent on build success or failure

---

## ⚙️ GitHub Actions CI/CD Workflow

### 📁 Workflow File

Located at `.github/workflows/ci-cd.yml`, the workflow includes:

1. **Install Dependencies**: Using pip
2. **Run Tests**: With `pytest`
3. **Build**: Prepare for deployment
4. **Deploy to Staging**: On push to `staging` branch
5. **Deploy to Production**: On release tag

### 🔐 Secrets Configuration

Add the following secrets in GitHub:
- `STAGING_API_KEY`
- `PROD_API_KEY`

### 🧪 Branch Strategy

- `main`: Development
- `staging`: Pre-production testing
- `release`: Tagged for production deployment

---

## 📸 Screenshots

Screenshots of pipeline executions are included in the `screenshots/` folder:
- Jenkins build, test, deploy stages
- GitHub Actions workflow runs

---

## 📄 Submission Instructions

- GitHub Repository: [https://github.com/Ravindra2409/B12flaskSampleApp]
- Submit this link via Vlearn in a `.txt`, `.docx`, or `.pdf` file
- Ensure screenshots and documentation are included

---
======
A Simple Example

```python
# save this as app.py
from flask import Flask

app = Flask(__name__)

@app.route("/")
def hello():
    return "Hello, World!"
```

```
$ flask run
  * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
```

======

## 🧠 Author

**Ravindra**  
Systems thinker and automation enthusiast  
Specialized in CI/CD, cloud infrastructure, and agentic workflows

---







[contrib]: https://palletsprojects.com/contributing/
