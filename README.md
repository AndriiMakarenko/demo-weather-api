# 🌤️ Demo Weather API

A **FastAPI** service that fetches weather data asynchronously, caches responses, and stores logs in **S3-compatible storage** and **DynamoDB** (or local equivalents).

## 🚀 Getting Started

Follow these steps to set up and run the project.

### 1️⃣ Install Poetry

Poetry is required for managing dependencies.

- **Installation guide:** [Poetry Docs](https://python-poetry.org/docs/#installation)

---

### 2️⃣ Install Docker

Docker is required to run the **DynamoDB**, **MinIO (S3 equivalent)**, **Redis**, and **FastAPI** containers.

- **Installation guide:** [Docker Docs](https://docs.docker.com/get-started/get-docker/)
- **On macOS (via Homebrew):**  
  ```sh
  brew install docker
  ```

---

### 3️⃣ Install Docker Compose

Docker Compose is used to manage multi-container environments.

- **Installation guide:** [Docker Compose Docs](https://docs.docker.com/compose/install/)
- **On macOS (via Homebrew):**  
  ```sh
  brew install docker-compose
  ```

---

### 4️⃣ Start the Environment

Run the following command from the project root:

```sh
docker-compose up -d
```

This will start:
- **DynamoDB Local** (`localhost:8000`)
- **MinIO (S3-compatible storage)** (`localhost:9000`)
- **Redis** (`localhost:6379`)
- **FastAPI (Weather API Service)** (`localhost:4242`)

---

### 5️⃣ Access the API Documentation

Once the environment is running, open **Swagger UI**:

🔗 **[http://localhost:4242/docs](http://localhost:4242/docs)**  

Here, you can test API endpoints interactively.

---

## 📂 Project Overview

```
weather-api/
│── app/
│   ├── api/v1/endpoints/        # API routes
│   ├── core/                    # Config & dependencies
│   ├── services/                # Business logic (weather, storage, db)
│   ├── models/                  # Pydantic models
│   ├── main.py                  # FastAPI entry point
│── tests/                       # Test suite
│── config.yaml                  # Configurations
│── .env                         # Environment variables
```

---

## 🛠️ Configuration

Modify `config.yaml` and `.env` to adjust **API keys, storage settings, and database connections**.

For local development, **MinIO** is used instead of AWS S3. In production, update `.env` to use **AWS S3** instead.

---

## ❓ Need Help?

- **FastAPI Docs:** [https://fastapi.tiangolo.com](https://fastapi.tiangolo.com)  
- **Boto3 (S3 SDK) Docs:** [https://boto3.amazonaws.com](https://boto3.amazonaws.com)  
- **Docker Docs:** [https://docs.docker.com](https://docs.docker.com)  

🚀 **Happy coding!**