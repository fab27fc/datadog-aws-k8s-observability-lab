# Datadog Overview

## What is Datadog?

Datadog is a cloud-based observability and monitoring platform used by DevOps, Cloud, Security, and SRE teams to monitor infrastructure, applications, logs, containers, and cloud services.

In this project, Datadog will be used as the central monitoring platform for AWS resources and a local Kubernetes cluster.

## Why use Datadog?

Datadog helps teams detect issues, visualize system health, centralize logs, and create alerts before problems affect users.

It is useful because it provides a single place to monitor different systems such as AWS, Kubernetes, containers, applications, and logs.

## Core Components

- Infrastructure Monitoring
- Log Management
- Kubernetes Monitoring
- Cloud Integrations
- Dashboards
- Monitors and Alerts
- Metrics Explorer

## Supported Integrations

Datadog supports integrations with cloud providers, containers, databases, CI/CD tools, and many third-party services.

For this project, the main integrations are:

- AWS
- Amazon CloudWatch
- Amazon EC2
- Kubernetes
- Docker
- Helm

## Architecture in this Project

Datadog will collect metrics from two environments:

1. AWS infrastructure using the AWS integration.
2. Local Kubernetes using the Datadog Agent installed with Helm.

```text
AWS CloudWatch Metrics ──► Datadog
Local Kubernetes Cluster ──► Datadog Agent ──► Datadog
