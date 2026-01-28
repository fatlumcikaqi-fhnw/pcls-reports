# PCLS Cloud Architecture & Migration Reports

This repository contains the technical documentation and architectural analysis for the **Parallel and Cloud Computing Systems (PCLS)** module at FHNW.

## 📋 Assessments Overview

### Assessment 1: Cloud Migration & Infrastructure Mapping
This assessment documents the migration of a microservice environment from a regional cloud provider to a global serverless infrastructure.

* **Description:** A complete "Shift" migration of a containerized application stack.
* **Source System (SWITCHengines):** Provisioned via **OpenTofu** (IaC) on OpenStack, with configuration management handled by **Ansible**.
* **Target System (AWS):** Re-architected for **AWS ECS Fargate**, utilizing a secure VPC setup with Private Subnets, NAT Gateways, and Application Load Balancers (ALB).
* **Migration Workflow:**
    1.  **Provisioning:** Setting up the AWS target environment using `tofu apply`.
    2.  **Validation:** Verifying DNS routing and service availability.
    3.  **Decommissioning:** Graceful shutdown of the legacy SwitchEngine infrastructure using `tofu destroy`.
* **Key Visuals:** Detailed architectural diagrams for both the internal system logic and external cloud integration.

### Assessment 2: [Title of Assessment 2]
* **Description:** [Enter a brief description of the task here].
* **Key Focus:** [e.g., Performance Benchmarking, Scaling, or Security].
* **Technologies:** [e.g., Azure, Kubernetes, or Prometheus].

---

### 📂 File Structure
* `assessment1.adoc`: Full technical report including detailed migration logic.
* `diagrams/`: High-resolution architectural schemas for **AWS/ECS Fargate** and **SWITCHengines**.

---
*Developed as part of the FHNW Bachelor of Science in Computer Science.*
