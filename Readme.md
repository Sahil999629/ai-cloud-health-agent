# AI-Powered Cloud Infrastructure Health Agent

> **Project built as part of my professional role at Coreweave Technologies**

_This project was designed, developed, and deployed during my tenure as a Cloud & AI Solutions Engineer at Coreweave Technologies. The focus was on creating an automated, production-ready AI solution for AWS cloud infrastructure monitoring, incident remediation, and intelligent reporting._

---

## Table of Contents

- [Project Overview](#project-overview)
- [Solution Architecture](#solution-architecture)
- [Key Features](#key-features)
- [Tech Stack](#tech-stack)
- [How It Works](#how-it-works)
- [Setup & Deployment](#setup--deployment)
- [Security Considerations](#security-considerations)
- [Troubleshooting & Support](#troubleshooting--support)
- [Project Impact](#project-impact)
- [Author / Role](#author--role)

---

## Project Overview

**AI-Powered Cloud Infrastructure Health Agent** is a production-grade, fully automated AWS cloud solution.  
It proactively monitors cloud infrastructure, auto-remediates common issues, and generates AI-driven incident summaries and cost optimization suggestions. The system ensures high uptime and maximum cloud efficiency for critical workloads.

---

## Solution Architecture

Architecture Diagram(![Architecture Diagram](https://sdmntprwestus3.oaiusercontent.com/files/00000000-6924-61fd-bf86-466c61f1c432/raw?se=2025-06-26T09%3A53%3A59Z&sp=r&sv=2024-08-04&sr=b&scid=e1e2a013-f1dd-5d41-b6ca-84352c627eb6&skoid=30ec2761-8f41-44db-b282-7a0f8809659b&sktid=a48cca56-e6da-484e-a814-9c849652bcb3&skt=2025-06-25T21%3A10%3A32Z&ske=2025-06-26T21%3A10%3A32Z&sks=b&skv=2024-08-04&sig=JXExSqSzv5W4nxr8lEFjJxRzmG3CTLzn5wHdHxYX8RQ%3D)) <!-- Replace with actual image path in your repo -->

- **AWS Lambda:** Executes health agent logic on demand.
- **Amazon S3:** Central storage for incident reports and AI summaries.
- **Amazon CloudWatch:** Monitors resources, triggers alarms.
- **Amazon SNS:** Publishes alerts, triggers Lambda.
- **OpenAI API:** Generates human-readable incident summaries and cost recommendations.
- **AWS IAM:** Ensures least-privilege permissions.
- **AWS CloudFormation:** Manages reproducible deployment.
- **GitHub Actions (CI/CD):** Automates code packaging and Lambda deployment.

---

## Key Features

- **Proactive Monitoring:** Real-time health checks across AWS services.
- **Automated Remediation:** Self-healing actions (e.g., EC2 reboot, resource scaling).
- **AI-Driven Reporting:** Incident summaries and cost recommendations using OpenAI.
- **Centralized Audit:** All actions and reports stored securely in S3.
- **Production-Grade Automation:** One-click deployment with CloudFormation and GitHub Actions.

---

## Tech Stack

- **Cloud:** AWS Lambda, S3, CloudWatch, SNS, IAM, CloudFormation
- **AI/ML:** OpenAI API
- **DevOps:** GitHub Actions (CI/CD)
- **Languages:** Python, YAML (CloudFormation)

---

## How It Works

1. **CloudWatch** monitors AWS infrastructure (CPU, memory, etc.).
2. On threshold breach, **CloudWatch** triggers an alarm to **SNS**.
3. **SNS** invokes the **Lambda** Health Agent.
4. **Lambda**:
   - Parses the incident
   - Attempts remediation (e.g., EC2 reboot)
   - Calls **OpenAI** for a human-readable summary & cost advice
   - Saves all details (raw report, AI summary, recommendations) to **S3**
5. All reports are time-stamped and easily auditable.

---

## Setup & Deployment

1. **Clone this repository** and review the code and CloudFormation template.
2. In AWS CloudFormation, **create a new stack** using the provided YAML template.
3. Upload the **Lambda package** (zip) to the designated S3 bucket.
4. Update Lambda code location if needed.
5. Connect **CloudWatch alarms** to the SNS topic.
6. **Test** with simulated incidents and verify S3 for new reports.

---

## Security Considerations

- **Least-privilege IAM roles**: Lambda access limited to necessary AWS services.
- **Secrets Management:** API keys stored in Lambda environment variables or AWS Secrets Manager.
- **Auditability:** All actions logged via CloudTrail.

---

## Troubleshooting & Support

| Issue              | Possible Cause                | Resolution                                 |
|--------------------|------------------------------|--------------------------------------------|
| Lambda errors      | Missing dependencies          | Ensure all code/libs zipped and deployed   |
| No S3 reports      | IAM permissions               | Update Lambda IAM role with S3 access      |
| No AI summary      | API key/network issue         | Check API key, VPC, and internet settings  |
| No remediation     | EC2 IAM permissions           | Add `ec2:RebootInstances` to role          |

**For any incidents, check CloudWatch Logs for step-by-step details.**

---

## Project Impact

This solution acts as a smart digital assistant for cloud servers, automatically detecting and resolving issues, generating easy-to-understand AI-powered summaries, and optimizing cloud costs.  
It is fully automated, secure, production-ready, and delivers measurable efficiency for cloud operations.

---

## Author / Role

**Sahil Kadam**  
Cloud Admin & AI Solutions Engineer  
Corewave Technologies  
_Navi Mumbai, India_

