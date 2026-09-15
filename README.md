# \# CodeAlpha Docker Web Server

# 

# A simple Flask web server containerized with Docker as part of the CodeAlpha DevOps Internship — Task 4: Web Server using Docker.

# 

# \## Project Overview

# 

# This project demonstrates how to:

# 

# \* Build a Docker image for a web application

# \* Run and manage Docker containers

# \* Expose a web application through a mapped port

# \* Implement container health monitoring

# \* Monitor container logs

# \* Perform Docker container lifecycle operations

# \* Troubleshoot port conflicts

# \* Test the application with Pytest

# 

# \## Technologies Used

# 

# \* Python

# \* Flask

# \* Docker

# \* Pytest

# \* PowerShell

# \* Git \& GitHub

# 

# \## Project Structure

# 

# ```text

# CodeAlpha\_Docker\_Web\_Server/

# ├── README.md

# ├── Dockerfile

# ├── requirements.txt

# ├── src/

# │   └── app.py

# ├── tests/

# │   └── test\_app.py

# └── screenshots/

# ```

# 

# \## Application Endpoints

# 

# \### Home

# 

# http://localhost:5001

# 

# Response:

# 

# CodeAlpha Docker Web Server is running successfully!

# 

# \### Health Check

# 

# http://localhost:5001/health

# 

# Response:

# 

# ```json

# {

# &#x20; "status": "healthy"

# }

# ```

# 

# \## Docker Configuration

# 

# The application is built using a lightweight Python 3.12 image.

# 

# The Dockerfile includes a health check that periodically verifies the application's `/health` endpoint.

# 

# ```dockerfile

# HEALTHCHECK --interval=30s --timeout=5s --start-period=5s --retries=3 CMD python -c "import urllib.request; urllib.request.urlopen('http://127.0.0.1:5000/health')"

# ```

# 

# \## Build the Docker Image

# 

# ```powershell

# docker build -t codealpha-docker-web-server:1.1 .

# ```

# 

# \## Run the Container

# 

# ```powershell

# docker run -d --name codealpha-web-server -p 5001:5000 codealpha-docker-web-server:1.1

# ```

# 

# The application is available at:

# 

# http://localhost:5001

# 

# \## Container Health Monitoring

# 

# Check the running containers:

# 

# ```powershell

# docker ps

# ```

# 

# The project successfully reports:

# 

# ```text

# Up ... (healthy)

# ```

# 

# The container health check repeatedly accesses the `/health` endpoint and receives HTTP 200 OK responses.

# 

# \## Container Logs

# 

# Logs can be viewed using:

# 

# ```powershell

# docker logs codealpha-web-server

# ```

# 

# The logs confirmed successful health checks:

# 

# ```text

# "GET /health HTTP/1.1" 200

# ```

# 

# \## Container Lifecycle Management

# 

# \### Stop the Container

# 

# ```powershell

# docker stop codealpha-web-server

# ```

# 

# \### View Stopped Containers

# 

# ```powershell

# docker ps -a

# ```

# 

# \### Start the Container

# 

# ```powershell

# docker start codealpha-web-server

# ```

# 

# \### Restart the Container

# 

# ```powershell

# docker restart codealpha-web-server

# ```

# 

# After restarting, the container successfully returned to:

# 

# ```text

# Up ... (healthy)

# ```

# 

# \## Troubleshooting

# 

# During deployment, port 5000 was already being used by another running Docker container.

# 

# Instead of stopping the existing application, the CodeAlpha container was mapped to host port 5001:

# 

# ```text

# 5001 → 5000

# ```

# 

# This allowed both applications to run simultaneously.

# 

# \## Automated Testing

# 

# The project includes Pytest tests for the home and health endpoints.

# 

# Run:

# 

# ```powershell

# python -m pytest

# ```

# 

# Test result:

# 

# ```text

# 2 passed in 0.22s

# ```

# 

# The tests verify:

# 

# \* Home endpoint returns HTTP 200

# \* Home endpoint contains the expected application message

# \* Health endpoint returns HTTP 200

# \* Health endpoint returns the expected JSON response

# 

# \## Key Docker Commands Demonstrated

# 

# ```powershell

# docker build

# docker run

# docker ps

# docker logs

# docker stop

# docker start

# docker restart

# docker ps -a

# docker rm

# ```

# 

# \## Learning Outcomes

# 

# This project provided hands-on experience with:

# 

# \* Docker image creation

# \* Container deployment

# \* Port mapping

# \* Container health checks

# \* Application monitoring

# \* Docker logs

# \* Container lifecycle management

# \* Troubleshooting port conflicts

# \* Automated application testing

# 

# \## CodeAlpha Internship

# 

# \*\*Program:\*\* CodeAlpha DevOps Internship

# 

# \*\*Task:\*\* Task 4 — Web Server using Docker

# 

# \*\*Repository:\*\* CodeAlpha\_Docker\_Web\_Server



