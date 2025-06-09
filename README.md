# 🛒 E-commerce Microservices Application (DevOps Project)

This project is a containerized microservices-based e-commerce application with services for **orders**, **products**, and **users**. It uses **Docker** for containerization, **Kubernetes** for orchestration, and **Jenkins** for CI/CD automation.

---

## 📦 Microservices

- Order Service: Handles order creation, updates, and retrieval.
- product Service: Manages product catalog and inventory.
- User Service: Manages user registration, authentication, and profiles.

Each microservice is developed using Flask and exposed via REST APIs.

### Clone the repository

```
git clone https://github.com/MulaBharathi/ecommerce-devops.git
cd ecommerce-devops
```

## 🐳 Docker: Build & Push

You can manually build and push Docker images:


# Build

```
docker build -t bharu2703/user-service ./user-service
docker build -t bharu2703/product-service ./product-service
docker build -t bharu2703/order-service ./order-service
```

# Push

```
docker push bharu2703/user-service
docker push bharu2703/product-service
docker push bharu2703/order-service
```

## ☸️ Kubernetes Deployment
Apply the manifests to deploy all services:

```
kubectl apply -f manifests/user-deployment.yaml
kubectl apply -f manifests/product-deployment.yaml
kubectl apply -f manifests/order-deployment.yaml
```