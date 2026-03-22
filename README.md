# Django Deployment on AWS ECS Fargate

A containerized Django application deployed using a serverless architecture on Amazon Web Services (AWS). This project demonstrates the integration of Docker, Amazon ECR, and ECS Fargate with an Application Load Balancer.

## Technical Stack
* **Web Framework:** Django (Python)
* **WSGI Server:** Gunicorn
* **Static Files:** WhiteNoise
* **Containerization:** Docker
* **Container Registry:** Amazon ECR
* **Orchestration:** Amazon ECS (Fargate Launch Type)
* **Networking:** Application Load Balancer (ALB), VPC, Security Groups

## Architecture Overview
The application is packaged as a Docker image and hosted in a private Amazon ECR repository. Traffic is managed by an Internet-facing Application Load Balancer (Port 80), which routes requests to a Target Group (Port 8000) associated with a Fargate Service.

## Key Implementation Steps
1. **Containerization:** Developed a Dockerfile to package the Django environment and Gunicorn server.
2. **Registry Management:** Authenticated and pushed the versioned image to Amazon ECR.
3. **Infrastructure Setup:** Provisioned a Target Group and an Application Load Balancer for high availability.
4. **Task Definition:** Configured an ECS Task Definition specifying CPU/Memory requirements and Port 8000 mappings.
5. **Service Deployment:** Launched an ECS Service using the Fargate launch type with automated public IP assignment.

## Live Application
The project is accessible via the ALB DNS:
http://django-alb-1447102134.ap-south-1.elb.amazonaws.com

---
