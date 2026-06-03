# Ì∫Ä DevOps Feedback Portal

A containerized two-tier web application built using **Flask**, **MySQL**, **Docker**, and **Docker Compose**. This project demonstrates the deployment and management of a multi-container application following DevOps best practices such as container networking, persistent storage, and health monitoring.

---

## Ì≥ñ Overview

DevOps Feedback Portal is a simple web application that allows users to submit feedback through a modern web interface. The feedback is stored in a MySQL database and displayed dynamically on the application dashboard.

The project is designed to showcase practical DevOps concepts including:

* Containerization using Docker
* Multi-container orchestration using Docker Compose
* Persistent storage with Docker Volumes
* Service-to-service communication using Docker Networks
* Application Health Checks
* Flask and MySQL integration

---

## ÌøóÔ∏è Architecture

```text
                +------------------+
                |      User        |
                +--------+---------+
                         |
                         v
                +------------------+
                |   Flask App      |
                |   (Frontend +    |
                |    Backend)      |
                +--------+---------+
                         |
                         v
                +------------------+
                |      MySQL       |
                |     Database     |
                +------------------+
```

---

## Ìª†Ô∏è Technology Stack

| Technology     | Purpose                 |
| -------------- | ----------------------- |
| Python         | Application Development |
| Flask          | Web Framework           |
| MySQL          | Database                |
| Docker         | Containerization        |
| Docker Compose | Container Orchestration |
| HTML/CSS       | User Interface          |

---

## ‚ú® Features

* Modern DevOps-themed user interface
* Submit and store feedback messages
* Display stored feedback dynamically
* MySQL database integration
* Dockerized deployment
* Health monitoring endpoint
* Persistent database storage
* Container networking
* Two-tier architecture implementation

---

## Ì≥Ç Project Structure

```text
devops-feedback-portal/
‚îÇ
‚îú‚îÄ‚îÄ app.py
‚îú‚îÄ‚îÄ Dockerfile
‚îú‚îÄ‚îÄ docker-compose.yml
‚îú‚îÄ‚îÄ requirements.txt
‚îú‚îÄ‚îÄ README.md
‚îÇ
‚îú‚îÄ‚îÄ templates/
‚îÇ   ‚îî‚îÄ‚îÄ index.html
‚îÇ
‚îú‚îÄ‚îÄ static/
‚îÇ   ‚îî‚îÄ‚îÄ style.css
‚îÇ
‚îî‚îÄ‚îÄ message.sql
```

---

## Ì∫Ä Getting Started

### Clone the Repository

```bash
git clone https://github.com/shamelsk/devops-feedback-portal.git

cd devops-feedback-portal
```

### Build and Start the Application

```bash
docker compose up --build -d
```

### Verify Running Containers

```bash
docker ps
```

Expected output:

```text
mysql       Up (healthy)
flask-app   Up (healthy)
```

---

## Ìºê Access the Application

Open your browser and visit:

```text
http://localhost:5000
```

or

```text
http://<server-ip>:5000
```

---

## Ìπ∫ Health Check

The application provides a health monitoring endpoint:

```text
/health
```

Example:

```bash
curl http://localhost:5000/health
```

Response:

```text
Application Healthy
```

---

## Ì≤æ Persistent Storage

The MySQL container uses Docker Volumes to ensure data persistence.

```yaml
volumes:
  mysql-data:
```

Database records remain available even after container restarts.

---

## Ì¥ó Container Networking

Docker Compose automatically creates an isolated network for service communication.

```yaml
networks:
  twotier:
```

The Flask application communicates with MySQL using the service name as the host:

```python
MYSQL_HOST=mysql
```

---

## Ì¥ß Useful Commands

### View Running Containers

```bash
docker ps
```

### View Application Logs

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

## Ì≥ö DevOps Concepts Demonstrated

* Docker Image Creation
* Docker Compose Orchestration
* Multi-Container Applications
* Container Networking
* Persistent Volumes
* Application Health Checks
* Service Dependency Management
* Flask‚ÄìMySQL Integration
* Container Troubleshooting
* Two-Tier Application Deployment

---

## Ì≥∏ Application Preview

Add a screenshot of the application here after deployment.

```text
screenshots/app-homepage.png
```

---

## Ì±®‚ÄçÌ≤ª Author

**Shamel Khan**

GitHub: https://github.com/shamelsk

Aspiring DevOps Engineer passionate about Cloud, Containers, Automation, and Infrastructure Technologies.

---

## Ì≥Ñ License

This project is open-source and available for learning, educational, and portfolio purposes.

