# DevOps Feedback Portal

A containerized two-tier web application built using Flask, MySQL, Docker, and Docker Compose.

This project demonstrates real-world DevOps concepts such as containerization, multi-container applications, persistent storage, container networking, and health monitoring.

---

# Architecture

```text
+------------------+
|      User        |
+--------+---------+
         |
         v
+------------------+
|    Flask App     |
| (Frontend/API)   |
+--------+---------+
         |
         v
+------------------+
|      MySQL       |
|    Database      |
+------------------+
```

---

# Features

* Flask web application
* MySQL database integration
* Dockerized deployment
* Docker Compose orchestration
* Persistent storage using Docker Volumes
* Container networking
* Application health checks
* Responsive user interface
* Two-tier architecture implementation

---

# Technology Stack

| Technology     | Purpose                    |
| -------------- | -------------------------- |
| Python         | Backend Development        |
| Flask          | Web Framework              |
| MySQL          | Database                   |
| Docker         | Containerization           |
| Docker Compose | Multi-Container Management |
| HTML           | Frontend Structure         |
| CSS            | Frontend Styling           |

---

# Project Structure

```text
devops-feedback-portal/
│
├── app.py
├── Dockerfile
├── docker-compose.yml
├── requirements.txt
├── README.md
├── message.sql
│
├── templates/
│   └── index.html
│
└── static/
    └── style.css
```

---

# Prerequisites

Before running the project, install the following:

## 1. Install Git

### Ubuntu

```bash
sudo apt update
sudo apt install git -y
```

### Verify Installation

```bash
git --version
```

---

## 2. Install Docker

### Ubuntu

```bash
sudo apt update

curl -fsSL https://get.docker.com -o get-docker.sh

sudo sh get-docker.sh
```

### Add Current User to Docker Group

```bash
sudo usermod -aG docker $USER
```

Logout and login again.

### Verify Installation

```bash
docker --version
```

---

## 3. Install Docker Compose

Most modern Docker installations include Docker Compose.

Verify:

```bash
docker compose version
```

If not installed:

```bash
sudo apt update

sudo apt install docker-compose-plugin -y
```

Verify again:

```bash
docker compose version
```

---

# Clone Repository

```bash
git clone https://github.com/shamelsk/devops-feedback-portal.git

cd devops-feedback-portal
```

---

# Build and Run the Application

Build and start all containers:

```bash
docker compose up --build -d
```

---

# Verify Running Containers

```bash
docker ps
```

Expected output:

```text
mysql
flask-app
```

---

# Access the Application

Open your browser:

```text
http://localhost:5000
```

or

```text
http://<server-ip>:5000
```

---

# Application Health Check

Verify application health:

```bash
curl http://localhost:5000/health
```

Expected output:

```text
Application Healthy
```

---

# View Container Logs

View all logs:

```bash
docker compose logs
```

Follow logs in real-time:

```bash
docker compose logs -f
```

---

# Useful Docker Commands

## Stop Containers

```bash
docker compose down
```

## Restart Containers

```bash
docker compose restart
```

## Rebuild Application

```bash
docker compose build --no-cache

docker compose up -d
```

## Remove Containers and Volumes

```bash
docker compose down -v
```

---

# Docker Components

## Flask Container

Responsibilities:

* Handle user requests
* Render frontend pages
* Process feedback submissions
* Communicate with MySQL

## MySQL Container

Responsibilities:

* Store feedback records
* Provide persistent data storage
* Serve database queries

---

# Networking

Docker Compose automatically creates an isolated network that allows containers to communicate securely.

The Flask application connects to MySQL using:

```python
MYSQL_HOST=mysql
```

---

# Persistent Storage

Database persistence is provided through Docker Volumes.

```yaml
volumes:
  mysql-data:
```

This ensures that data remains available even after container restarts.

---

# DevOps Concepts Demonstrated

* Docker Image Creation
* Multi-Container Applications
* Docker Compose
* Container Networking
* Persistent Volumes
* Health Checks
* Service Dependency Management
* Flask and MySQL Integration
* Infrastructure Troubleshooting
* Two-Tier Architecture

---

# Author

Shamel Khan

GitHub: https://github.com/shamelsk

Aspiring DevOps Engineer focused on Cloud Computing, Containers, Automation, and Infrastructure Technologies.

