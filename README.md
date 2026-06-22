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



  
  | Component               | Purpose                   |
| ----------------------- | ------------------------- |
| Prometheus              | Metrics collection        |
| Grafana                 | Visualization             |
| Loki                    | Log aggregation           |
| Promtail                | Log shipping              |
| Alertmanager            | Alert management          |
| Node Exporter           | Node metrics              |
| kube-state-metrics      | Kubernetes object metrics |
| OpenTelemetry Collector | Telemetry pipeline        |
| Zipkin                  | Distributed tracing       |
| Pushgateway             | Push-based metrics        |

