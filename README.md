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

### Assessment 2: Cloud-to-Cloud Migration (AWS to Azure)
This assessment demonstrates a high-availability migration of a stateful chatbot ecosystem from a containerized AWS architecture to a serverless Azure environment.

* **Description:** A complex automated migration involving database synchronization and zero-downtime DNS cutover.
* **Source System (AWS):** A microservice stack running on **ECS Fargate** within a private VPC, utilizing **DynamoDB** for persistence and **Route53** for traffic management.
* **Target System (Azure):** A serverless architecture using **Azure Function Apps (Flex Consumption)**, **CosmosDB**, and **Azure AI Foundry** (GPT-4o-mini integration).
* **Migration Strategy:** 1. **Automated Provisioning:** Deploying the full Azure stack via **OpenTofu**.
    2. **Stateful Migration:** A custom migration script that pauses the source (AWS), replicates data from DynamoDB to CosmosDB, and resumes operations on the target (Azure).
    3. **Traffic Cutover:** Updating **Route53 DNS** records to redirect global traffic from the AWS ALB to the new Azure Function endpoints.
* **Key Focus:** Data consistency during migration, Infrastructure as Code (IaC) parity, and serverless AI integration.
* **Technologies:** OpenTofu, AWS (ECS, DynamoDB), Azure (Functions, CosmosDB, AI Foundry), Shell Scripting.

---
*Developed as part of the FHNW Bachelor of Science in Computer Science.*
