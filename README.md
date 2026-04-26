# 🚀 DevOps Monitoring System (AWS + Kubernetes + CI/CD + Alerts)

## 🎯 Objective

The objective of this project is to design and implement a complete DevOps monitoring system that integrates cloud infrastructure, CI/CD pipeline, containerization, orchestration, monitoring, and alerting tools.

---

## 🧰 Tools & Technologies Used

* AWS EC2 (Ubuntu)
* Jenkins (CI/CD)
* Docker (Containerization)
* Kubernetes (Minikube)
* Prometheus (Monitoring)
* Grafana (Visualization)
* Alertmanager (Alerting)
* Git & GitHub (Version Control)

---

## 🧠 System Architecture

The system follows a complete DevOps lifecycle:

1. Developer pushes code to GitHub
2. Jenkins pipeline triggers automatically
3. Docker image is built
4. Application is deployed to Kubernetes
5. Prometheus monitors system metrics
6. Grafana visualizes data in dashboards
7. Alertmanager sends alerts on failures

---

## ⚙️ Project Structure

```
devops-monitoring-project/
│
├── Jenkinsfile
├── Dockerfile
├── README.md
│
├── k8s/
│   └── deployment.yaml
│
├── monitoring/
│   ├── prometheus.yaml
│   ├── prometheus-rules.yaml
│   └── alertmanager.yaml
```

---

## ☁️ Phase 1: Infrastructure Setup (AWS)

* Launched EC2 instance (Ubuntu 22.04)
* Opened required ports:

  * 22 (SSH)
  * 8080 (Jenkins)
  * 9090 (Prometheus)
  * 3000 (Grafana)

### Installed tools:

```bash
sudo apt update
sudo apt install docker.io git -y
sudo systemctl start docker
sudo usermod -aG docker ubuntu
```

---

## 🐳 Phase 2: CI/CD using Jenkins

* Installed Jenkins on EC2
* Accessed via:

```
http://<EC2-IP>:8080
```

### Jenkins Pipeline:

* Builds Docker image
* Deploys to Kubernetes

---

## ☸️ Phase 3: Kubernetes Setup

* Installed Minikube
* Created deployment using `deployment.yaml`

### Deployment Features:

* 2 replicas
* Nginx container
* Exposed on port 80

---

## 📊 Phase 4: Monitoring (Prometheus + Grafana)

* Installed using Helm:

```bash
helm install monitoring prometheus-community/kube-prometheus-stack
```

### Prometheus:

* Collects metrics from system and containers

### Grafana:

* Displays dashboards:

  * Node metrics
  * Pod usage
  * Cluster health

### Access Grafana:

```bash
kubectl port-forward svc/monitoring-grafana 3000:80
```

Open: http://localhost:3000

---

## 🔔 Phase 5: Alerting (Alertmanager)

* Configured alert rules in Prometheus
* Integrated Alertmanager for notifications

### Example Alerts:

* High CPU usage
* Pod failure
* Node down

---

## 🔄 Phase 6: CI/CD + Monitoring Integration

Complete flow:

1. Code pushed to GitHub
2. Jenkins builds Docker image
3. Deploys to Kubernetes
4. Prometheus monitors application
5. Grafana visualizes metrics
6. Alertmanager sends alerts

---

## 📊 Expected Output

* Live dashboards in Grafana
* Automated deployment via Jenkins
* Real-time monitoring using Prometheus
* Alerts triggered on failures

---

## 🎓 Viva Questions

### DevOps

* What is CI/CD pipeline?
* Difference between CI and CD?

### Kubernetes

* What is a Pod?
* Difference between Deployment and Service?

### Monitoring

* What is Prometheus scraping?
* Why is Grafana used?

### Alerts

* What is Alertmanager?
* What are alert rules?

---

## 📝 Result

Successfully designed and implemented a complete DevOps Monitoring System 


