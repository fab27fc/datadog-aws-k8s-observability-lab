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
```

---

# Datadog Account Setup

## Objective

Create a Datadog account that will be used throughout this project to monitor AWS infrastructure and a local Kubernetes cluster.

## Prerequisites

Before creating the account, ensure you have:

- A valid email address
- An AWS account
- Internet access

## Creating a Datadog Account

1. Navigate to the Datadog website: https://datadoghq.com
2. Create a Trial account.
3. Verify your email address.
4. Log in to the Datadog dashboard.
4.1 Choose Infrastructure & backend applications option ( It is designed specifically for these use cases).

It will guide you through setting up:

Infrastructure Monitoring
Cloud Integrations
Host Monitoring
Kubernetes Monitoring
Datadog Agent
Metrics Collection
(This perfectly matches the scope of our project).

4.2 Add your Cloud Provider -> AWS

5. Connect to your AWS account to monitor your cloud infrastructure

# AWS Integration
Your settings look correct:

- CloudFormation
- Region: us-east-1
- Deploy log forwarder: OFF
- Detect security issues: No

Now click:

* Open in AWS Console
<img width="1360" height="641" alt="image" src="https://github.com/user-attachments/assets/dec143a9-e07d-4822-b4c4-0f43cc870d85" />

Then, in the CloudFormation page:

Leave all the generated values as they are.
Do not choose an IAM Role for CloudFormation.
Check both boxes at the bottom:
<img width="1337" height="210" alt="image" src="https://github.com/user-attachments/assets/5eb5b6a8-04d1-49a0-af30-15c2f3b83a01" />

Click Create stack.
Wait until the main stack DatadogIntegration reaches CREATE_COMPLETE.

<img width="1271" height="970" alt="image" src="https://github.com/user-attachments/assets/ec73091b-86dc-4bd9-aa22-a3c61dbbc06d" />

I will start to run CloudFront:
<img width="1362" height="782" alt="image" src="https://github.com/user-attachments/assets/df66546d-d465-4c76-b296-f12d74f47a5a" />

Integration has been completed:
<img width="1102" height="787" alt="image" src="https://github.com/user-attachments/assets/3c738b5e-c9ad-452a-8b48-7b98368eb159" />

## Why use CloudFormation?

Datadog provides an official CloudFormation template that automates the deployment of all AWS resources required for the integration.

Using CloudFormation ensures that the deployment is:

- Repeatable
- Consistent
- Easy to maintain
- Supported by Datadog

## Resources Created

The CloudFormation template creates:

- IAM Role
- IAM Policies
- Cross-account trust relationship
- Datadog AWS Integration
- (Optional) Lambda Log Forwarder

## CloudFormation Deployment

Datadog provides an official AWS CloudFormation template that automates the deployment of the resources required for the AWS integration.

The template creates the IAM roles and permissions needed for Datadog to securely access AWS metrics and metadata.

### Parameters

| Parameter | Description |
|-----------|-------------|
| Stack Name | Name of the CloudFormation stack. |
| Datadog API Key | Authenticates data sent from AWS to Datadog. |
| Datadog Application Key | Allows the integration to access the Datadog API. |
| Datadog Site | Specifies the Datadog site where the data will be sent. |








## Creating an API Key

The API Key authenticates the Datadog Agent and other services when sending metrics, logs, and events to Datadog.

Steps:

1. Open **Organization Settings**.
2. Navigate to **API Keys**.
3. Click **New Key**.
4. Save the generated API Key securely.

## Creating an Application Key

The Application Key is used by applications and automation tools to access the Datadog API.

Steps:

1. Navigate to **Application Keys**.
2. Create a new Application Key.
3. Save it securely.

## Validation

The setup is considered successful when:

- The Datadog dashboard is accessible.
- An API Key has been created.
- An Application Key has been created.

## Screenshots

The following screenshots will be added during the implementation:

- Login page
- Datadog dashboard
- API Key creation
- Application Key creation
