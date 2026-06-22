# kubernetes-observability-platform
                Kubernetes Cluster
                        │
        ┌───────────────┼────────────────┐
        │               │                │
     Metrics          Logs            Traces
        │               │                │
        ▼               ▼                ▼
 Node Exporter      Promtail      OpenTelemetry
 kube-state-metrics    │             Collector
        │               │                │
        ▼               ▼                ▼
   Prometheus         Loki           Zipkin
        │               │                │
        └───────────────┴────────────────┘
                        │
                        ▼
                    Grafana
