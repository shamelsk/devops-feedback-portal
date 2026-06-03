# íº DevOps Feedback Portal

A containerized two-tier web application built using **Flask**, **MySQL**, **Docker**, and **Docker Compose**. This project demonstrates the deployment and management of a multi-container application following DevOps best practices such as container networking, persistent storage, and health monitoring.

---

## í³ Overview

DevOps Feedback Portal is a simple web application that allows users to submit feedback through a modern web interface. The feedback is stored in a MySQL database and displayed dynamically on the application dashboard.

The project is designed to showcase practical DevOps concepts including:

* Containerization using Docker
* Multi-container orchestration using Docker Compose
* Persistent storage with Docker Volumes
* Service-to-service communication using Docker Networks
* Application Health Checks
* Flask and MySQL integration

---

## í¿ï¸ Architecture

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

## í» ï¸ Technology Stack

| Technology     | Purpose                 |
| -------------- | ----------------------- |
| Python         | Application Development |
| Flask          | Web Framework           |
| MySQL          | Database                |
| Docker         | Containerization        |
| Docker Compose | Container Orchestration |
| HTML/CSS       | User Interface          |

---

## â¨ Features

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

## í³ Project Structure

```text
devops-feedback-portal/
â
âââ app.py
âââ Dockerfile
âââ docker-compose.yml
âââ requirements.txt
âââ README.md
â
âââ templates/
â   âââ index.html
â
âââ static/
â   âââ style.css
â
âââ message.sql
```

---

## íº Getting Started

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

## í¼ Access the Application

Open your browser and visit:

```text
http://localhost:5000
```

or

```text
http://<server-ip>:5000
```

---

## í¹º Health Check

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

## í²¾ Persistent Storage

The MySQL container uses Docker Volumes to ensure data persistence.

```yaml
volumes:
  mysql-data:
```

Database records remain available even after container restarts.

---

## í´ Container Networking

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

## í´§ Useful Commands

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

## í³ DevOps Concepts Demonstrated

* Docker Image Creation
* Docker Compose Orchestration
* Multi-Container Applications
* Container Networking
* Persistent Volumes
* Application Health Checks
* Service Dependency Management
* FlaskâMySQL Integration
* Container Troubleshooting
* Two-Tier Application Deployment

---

## í³¸ Application Preview

Add a screenshot of the application here after deployment.

```text
screenshots/app-homepage.png
```

---

## í±¨âí²» Author

**Shamel Khan**

GitHub: https://github.com/shamelsk

Aspiring DevOps Engineer passionate about Cloud, Containers, Automation, and Infrastructure Technologies.

---

## í³ License

This project is open-source and available for learning, educational, and portfolio purposes.

