# ISEC6000--SecureDevOps

# ISEC6000 Secure DevOps Assignment 1

## Project Overview
This project involves building, deploying, and securing a microservices-based e-commerce application, Saleor, using modern DevOps practices. The platform comprises several components including the Saleor API, Dashboard, PostgreSQL database, and Redis cache, deployed within a Kubernetes cluster on GKE.

## Objectives
1. Design and deploy a scalable microservices architecture using Docker and Kubernetes.
2. Implement robust security measures, including running containers as non-root users, setting resource limits, and using vulnerability scanning tools.
3. Integrate continuous monitoring and logging for proactive application performance and security management.

## Repository Structure
```
|-- saleor-platform/
|-- docker-compose.yml
|-- README.md
```

## Technologies Used
- **Docker**: For containerizing the application.
- **Kubernetes (GKE)**: For orchestration and scaling of microservices.
- **PostgreSQL**: For persistent database storage.
- **Redis**: For caching and improving application performance.
- **Trivy**: For scanning Docker containers for vulnerabilities.

## Prerequisites
Before setting up, ensure you have:
- Docker (v27.1.2 or higher)
- Kubernetes and kubectl (v1.18 or higher)
- A Google Cloud account to use Google Kubernetes Engine (GKE)
- Python 3.9 or higher installed

## Installation

1. **Clone the Saleor Platform Repository**
   ```
   git clone https://github.com/saleor/saleor-platform
   cd saleor-platform
   ```

2. **Customize Docker Compose**
   - Modify the `docker-compose.yml` file to configure ports and services.
   - Ensure port `9002` is assigned to the Saleor Dashboard.

3. **Create a Kubernetes Cluster in GKE**
   ```bash
   gcloud container clusters create saleor-cluster --num-nodes=3
   ```

5. **Access the Saleor Dashboard**
   - The dashboard should be accessible via `http://<Cluster-IP>:9002`.

## Security Measures
- **Non-root Containers**: Containers are configured to run as non-root users.
- **Vulnerability Scanning**: Use Trivy to scan for vulnerabilities in Docker images.
- **Resource Limits**: CPU and memory limits are set on containers to prevent over-utilization.

## Running Trivy Security Scan
1. **Install Trivy**:
   ```bash
   sudo apt-get install trivy
   ```
2. **Scan Docker Images**:
   ```bash
   trivy image saleor-platform
   ```

## Architecture Diagram
(Include the architecture diagram here, if available)

## Known Issues
- First-time deployment may take longer than expected. Restart the services if needed.

## Authors
- **urva patel (Student ID: 21717051)**

