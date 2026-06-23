# Installation Guide

## Requirements

- Kubernetes Cluster
- Helm 3
- kubectl

---

## Install Prometheus Stack

```bash
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts

helm repo update

helm install prometheus prometheus-community/kube-prometheus-stack \
-n monitoring --create-namespace
```

---

## Install Loki

```bash
helm repo add grafana https://grafana.github.io/helm-charts

helm repo update

helm install loki grafana/loki \
-n monitoring
```

---

## Install Promtail

```bash
helm install promtail grafana/promtail \
-n monitoring
```

---

## Install Grafana

Grafana is deployed as part of the kube-prometheus-stack.

---

## Install OpenTelemetry Collector

```bash
helm install otel open-telemetry/opentelemetry-collector \
-n monitoring
```

---

## Install Zipkin

```bash
kubectl apply -f zipkin.yaml
```

---

## Verify

```bash
kubectl get pods -n monitoring
```

All pods should be in Running state.

---

## Access Grafana

```bash
kubectl port-forward svc/grafana 3000:80 -n monitoring
```

Open:

http://localhost:3000
