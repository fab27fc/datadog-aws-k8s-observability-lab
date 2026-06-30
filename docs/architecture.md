# Architecture

## Objective

The objective of this project is to build an observability platform capable of monitoring AWS infrastructure and a local Kubernetes cluster using Datadog.

## High-Level Architecture

The solution consists of three main components:

1. AWS Infrastructure
2. Datadog Platform
3. Local Kubernetes Cluster

Datadog acts as the central monitoring platform, collecting metrics, logs, and events from both AWS services and the Kubernetes cluster.

## Components

### AWS Account

Hosts the cloud infrastructure that will be monitored.

### IAM Role

Allows Datadog to securely access AWS resources without using long-term credentials.

### Amazon CloudWatch

Provides AWS metrics that Datadog collects and visualizes.

### Amazon EC2

Represents the compute resources monitored by Datadog.

### Datadog

Central observability platform that aggregates metrics, logs, traces, and alerts.

### Local Kubernetes Cluster

Hosts the containerized workloads running on the local machine.

### Datadog Agent

Collects metrics, logs, and Kubernetes events.

### Helm

Used to deploy and manage the Datadog Agent within the Kubernetes cluster.
