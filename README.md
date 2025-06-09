# 🛒 E-commerce Microservices Application (DevOps Project)

This project is a containerized microservices-based e-commerce application with services for **orders**, **products**, and **users**. It uses **Docker** for containerization, **Kubernetes** for orchestration, and **Jenkins** for CI/CD automation.

---

## 📦 Microservices

- Order Service: Handles order creation, updates, and retrieval.
- Product Service: Manages product catalog and inventory.
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

### CI/CD With Jenkins
Using Jenkins Pipeline
The Jenkins pipeline automates building, pushing images, and deploying to Kubernetes. The pipeline script is in the jenkins directory

## ☸️ Kubernetes Deployment
Apply the manifests to deploy all services:

```
kubectl apply -f manifests/user-deployment.yaml
kubectl apply -f manifests/product-deployment.yaml
kubectl apply -f manifests/order-deployment.yaml
```

## 📈 Monitoring with Prometheus & Grafana

This project includes monitoring for all microservices using **Prometheus** and **Grafana**.

### Prometheus
- Collects metrics from Flask apps exposed via `/metrics` endpoint using `prometheus_client`.
- Deployed in Kubernetes using `prometheus-deployment.yaml`.

### Grafana
- Visualizes metrics collected by Prometheus.
- Dashboards display real-time service stats like request count, latency, CPU/memory usage.
- Accessible via NodePort or Ingress, based on your configuration.

### To Deploy:

```
kubectl apply -f prometheus-grafana
```
