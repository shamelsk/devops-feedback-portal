# DevOps Feedback Portal

A containerized two-tier web application built using Flask, MySQL, Docker, and Docker Compose.

The application allows users to submit feedback through a web interface and stores it in a MySQL database. The project demonstrates containerized application deployment, persistent storage, service networking, and health monitoring using Docker.

Built as part of hands-on DevOps learning and containerization practice.

---

## Tech Stack

| Component        | Technology     |
| ---------------- | -------------- |
| Backend          | Flask          |
| Database         | MySQL 5.7      |
| Language         | Python 3.9     |
| Containerization | Docker         |
| Orchestration    | Docker Compose |
| Frontend         | HTML, CSS      |

---

## Features

* Two-tier architecture
* Flask web application
* MySQL database integration
* Dockerized deployment
* Docker Compose orchestration
* Persistent storage using Docker Volumes
* Container networking
* Application health checks
* Responsive user interface

---

## Architecture

```text
+-------------+
|    User     |
+------+------+
       |
       v
+-------------------+
|    Flask App      |
|  Frontend + API   |
+---------+---------+
          |
          v
+-------------------+
|      MySQL        |
|     Database      |
+-------------------+
```

---

## Project Structure

```text
devops-feedback-portal/
├── app.py
├── Dockerfile
├── docker-compose.yml
├── requirements.txt
├── message.sql
├── README.md
├── templates/
│   └── index.html
└── static/
    └── style.css
```

---

## Prerequisites

Install the following software before running the application:

### Git

Ubuntu:

```bash
sudo apt update
sudo apt install git -y
```

Verify:

```bash
git --version
```

### Docker

Ubuntu:

```bash
curl -fsSL https://get.docker.com -o get-docker.sh

sudo sh get-docker.sh
```

Verify:

```bash
docker --version
```

### Docker Compose

Verify:

```bash
docker compose version
```

If not installed:

```bash
sudo apt install docker-compose-plugin -y
```

---

## Quick Start

### Clone Repository

```bash
git clone https://github.com/shamelsk/devops-feedback-portal.git

cd devops-feedback-portal
```

### Build and Run

```bash
docker compose up -d
```

### Verify Containers

```bash
docker ps
```

Expected containers:

```text
mysql
flask-app
```

---

## Access Application

Open:

```text
http://localhost:5000
```

or

```text
http://<server-ip>:5000
```

---

## Health Check

The application exposes a health endpoint used for monitoring container health.

### Endpoint

```text
/health
```

### Test

```bash
curl http://localhost:5000/health
```

Expected Response:

```text
Application Healthy
```

---

## Docker Components

### Flask Container

Responsibilities:

* Handle user requests
* Process feedback submissions
* Render frontend pages
* Communicate with MySQL

### MySQL Container

Responsibilities:

* Store application data
* Persist records using Docker Volumes
* Serve database queries

---

## Persistent Storage

The MySQL database uses Docker Volumes to preserve data across container restarts.

```yaml
volumes:
  mysql-data:
```

---

## Networking

Docker Compose automatically creates an isolated network allowing communication between containers.

The Flask application connects to MySQL using:

```python
MYSQL_HOST=mysql
```

---

## Useful Commands

### View Running Containers

```bash
docker ps
```

### View Logs

```bash
docker compose logs -f
```

### Stop Application

```bash
docker compose down
```

### Rebuild Application

```bash
docker compose build --no-cache

docker compose up -d
```

### Remove Containers and Volumes

```bash
docker compose down -v
```

---

## DevOps Concepts Demonstrated

* Docker Image Creation
* Multi-Container Applications
* Docker Compose
* Container Networking
* Persistent Volumes
* Health Checks
* Service Dependency Management
* Flask–MySQL Integration
* Infrastructure Troubleshooting
* Two-Tier Application Deployment

---

## Author

**Shamel Khan**

GitHub: https://github.com/shamelsk

Aspiring DevOps Engineer focused on Cloud Computing, Containers, Automation, and Infrastructure Technologies.

