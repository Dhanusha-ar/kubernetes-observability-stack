# kubernetes-observability-stack


## Overview

This project implements a complete observability stack for Kubernetes environments using Prometheus, Grafana, Loki, and Promtail. It enables centralized monitoring and logging for containerized applications.

The stack collects infrastructure metrics and application logs, providing visualization and alerting capabilities through Grafana dashboards.

---

## Tools Used

Kubernetes  
Prometheus  
Grafana  
Loki  
Promtail  
Node Exporter  

---

## Architecture

Metrics Flow

Application / Node Metrics  
↓  
Prometheus  
↓  
Grafana Dashboards  

Log Flow

Application Logs  
↓  
Promtail  
↓  
Loki  
↓  
Grafana  

---

## Components

### Prometheus
Prometheus collects metrics from Kubernetes nodes and services.

### Grafana
Grafana provides visualization dashboards for metrics and logs.

### Loki
Loki is used for centralized log aggregation.

### Promtail
Promtail collects logs from containers and sends them to Loki.

---

## Deployment Steps

### 1. Create Kubernetes Namespace

kubectl create namespace monitoring

---

### 2. Deploy Prometheus

kubectl apply -f prometheus/prometheus-config.yaml

---

### 3. Deploy Loki

kubectl apply -f loki/loki-deployment.yaml

---

### 4. Deploy Promtail

kubectl apply -f promtail/promtail-config.yaml

---

### 5. Deploy Grafana

kubectl apply -f grafana/grafana-deployment.yaml

---

## Access Grafana

kubectl port-forward service/grafana 3000:3000 -n monitoring

Open browser:

http://localhost:3000

Default credentials

admin / admin

---

## Sample Dashboards

- Kubernetes cluster monitoring
- CPU and memory utilization
- Container logs

---

## Project Goals

Provide a centralized monitoring platform for Kubernetes clusters.  
Enable real-time metrics visualization and log aggregation.  
Demonstrate DevOps observability practices.

---

## Future Improvements

Add Alertmanager for automated alerts.  
Add Helm charts for simplified deployments.  
Integrate Slack or email notifications.
