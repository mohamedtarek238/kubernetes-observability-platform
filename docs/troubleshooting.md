# Troubleshooting

This document summarizes common issues encountered while deploying and maintaining the monitoring platform.

---

## Prometheus Target Down

### Symptoms

Some targets appear as DOWN.

### Resolution

- Verify ServiceMonitor configuration.
- Check pod status.
- Confirm endpoints are reachable.

---

## Grafana Shows No Data

### Symptoms

Dashboards display "No Data".

### Resolution

- Verify Prometheus datasource.
- Check Prometheus targets.
- Confirm scrape jobs are healthy.

---

## Loki Not Receiving Logs

### Symptoms

No logs appear in Grafana Explore.

### Resolution

- Verify Promtail pods.
- Check Promtail configuration.
- Inspect Loki logs.

---

## High Memory Usage

### Symptoms

Memory alerts triggered.

Examples:

- HostOutOfMemory
- HostMemoryUnderPressure

### Resolution

- Inspect pod memory consumption.
- Review resource requests and limits.
- Analyze node usage using kubectl top.

---

## Swap Usage Alert

### Symptoms

HostSwapIsFillingUp alert fired.

### Resolution

- Investigate memory pressure.
- Review workload resource consumption.
- Tune application memory usage.

---

## Pod CrashLoopBackOff

### Resolution

```bash
kubectl describe pod <pod-name>

kubectl logs <pod-name>
```

---

## Alertmanager Notifications Not Working

Check:

- Alertmanager configuration
- Email credentials
- Slack Webhook
- Network connectivity

---

## Useful Commands

```bash
kubectl get pods -n monitoring

kubectl top nodes

kubectl top pods -n monitoring

kubectl logs <pod-name> -n monitoring

kubectl describe pod <pod-name>

kubectl get svc -n monitoring
```
