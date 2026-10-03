## Task 19 - Deploy Dockerized Application on AWS ECS

### Architecture
- Amazon ECR for Docker image storage
- Amazon ECS with AWS Fargate
- Application Load Balancer
- Frontend service on port 8080
- Backend service on port 5000
- MongoDB container on port 27017
- ALB health checks for ECS services

### ECR Repositories
- frontend
- backend
- mongodb

### ECS Services
- ecommerce-frontend-service
- ecommerce-backend-service

### Load Balancing
Application Load Balancer: ecommerce-alb

Frontend:
- Container port: 8080
- Target group: ecommerce-frontend-tg
- Health check path: /

Backend:
- Container port: 5000
- Target group: ecommerce-backend-tg
- Health check path: /health

### Backend Health Check
The backend exposes the following endpoint:

GET /health

Expected response:

{"status":"ok"}

### Deployment Verification
- Frontend ECS service is running.
- Backend ECS service is running.
- Frontend target is healthy.
- Backend target is healthy.
- Application is accessible through the Application Load Balancer.
- Backend health endpoint returns HTTP 200.

### Result
The Dockerized e-commerce application was successfully deployed on AWS ECS using Fargate and exposed through an Application Load Balancer.
