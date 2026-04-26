# DevOps Monitoring Project

## Tools Used
- AWS EC2
- Jenkins
- Docker
- Kubernetes
- Prometheus
- Grafana
- Alertmanager

## Flow
1. Code pushed to GitHub
2. Jenkins builds Docker image
3. Kubernetes deploys app
4. Prometheus monitors
5. Grafana shows dashboards
6. Alertmanager sends alerts

## Grafana Access
kubectl port-forward svc/monitoring-grafana 3000:80

http://localhost:3000