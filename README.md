# DevOps Feedback Portal

## Overview

DevOps Feedback Portal is a containerized two-tier web application built using Flask, MySQL, Docker, and Docker Compose.

The application allows users to submit feedback through a web interface. Submitted feedback is stored in a MySQL database and displayed dynamically on the application dashboard.

This project demonstrates core DevOps concepts including containerization, multi-container deployments, persistent storage, health checks, and container networking.

---

## Architecture

```text
+------------------+
|      User        |
+--------+---------+
         |
         v
+------------------+
|    Flask App     |
| (Frontend + API) |
+--------+---------+
         |
         v
+------------------+
|      MySQL       |
|    Database      |
+------------------+
```

---

## Technology Stack

| Technology     | Purpose                       |
| -------------- | ----------------------------- |
| Python         | Backend Development           |
| Flask          | Web Framework                 |
| MySQL          | Database                      |
| Docker         | Containerization              |
| Docker Compose | Multi-Container Orchestration |
| HTML           | Frontend Structure            |
| CSS            | Frontend Styling              |

---

## Features

* Two-tier application architecture
* Flask backend integration
* MySQL database connectivity
* Dockerized deployment
* Docker Compose orchestration
* Persistent database storage using Docker Volumes
* Container networking
* Application health monitoring
* Modern responsive user interface

---

## Project Structure

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

## Prerequisites

Before running the application, ensure the following tools are installed:

* Docker
* Docker Compose
* Git

---

## Installation

### Clone the Repository

```bash
git clone https://github.com/shamelsk/devops-feedback-portal.git

cd devops-feedback-portal
```

### Build and Start Containers

```bash
docker compose up --build -d
```

### Verify Running Containers

```bash
docker ps
```

Expected containers:

```text
mysql
flask-app
```

---

## Access the Application

Open a browser and navigate to:

```text
http://localhost:5000
```

or

```text
http://<server-ip>:5000
```

---

## Health Check

The application exposes a health endpoint:

```text
/health
```

Test the endpoint:

```bash
curl http://localhost:5000/health
```

Expected response:

```text
Application Healthy
```

---

## Docker Components

### Flask Container

Responsible for:

* Handling user requests
* Rendering web pages
* Connecting to MySQL
* Processing feedback submissions

### MySQL Container

Responsible for:

* Storing application data
* Maintaining persistent records
* Serving database queries

---

## Networking

Docker Compose creates an isolated network allowing the Flask application to communicate with MySQL using the service name:

```python
MYSQL_HOST=mysql
```

---

## Persistent Storage

Database persistence is achieved using Docker Volumes:

```yaml
volumes:
  mysql-data:
```

This ensures that database records remain available even after container restarts.

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

### Stop Containers

```bash
docker compose down
```

### Rebuild Containers

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
* Container Lifecycle Management
* Docker Compose
* Multi-Container Applications
* Persistent Volumes
* Container Networking
* Health Checks
* Service Dependency Management
* Flask and MySQL Integration
* Infrastructure Troubleshooting

---

## Author

Shamel Khan

GitHub: https://github.com/shamelsk

DevOps and Cloud Computing Enthusiast

