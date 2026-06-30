# AWS + Kubernetes Observability Lab with Datadog

## Overview

This project demonstrates how to monitor AWS infrastructure and a local Kubernetes cluster using Datadog.

The lab includes:

- AWS integration with Datadog
- EC2 monitoring
- CloudWatch metrics
- Local Kubernetes monitoring
- Datadog Agent installation with Helm
- Container logs
- Basic dashboards and alerts

## Architecture

```text
Datadog
 ├── AWS Integration
 │    ├── CloudWatch Metrics
 │    └── EC2 Monitoring
 │
 └── Local Kubernetes Cluster
      ├── Datadog Agent
      ├── Cluster Agent
      ├── Pods
      ├── Deployments
      └── Container Logs
