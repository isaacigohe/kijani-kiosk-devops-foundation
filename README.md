# KijaniKiosk DevOps Foundation

## Overview
This repository contains the engineering foundations and DevOps Starter Kit for the **KijaniKiosk** online platform. It documents key architectural decisions around cloud service models, region/multi-AZ reliability, least-privilege security policies, network subnet segmentation, and DevOps delivery workflows before deploying production workloads.

---

## Project Structure
```text
kijani-kiosk-devops-foundation/
├── README.md                          # Project overview and navigation
└── starter-kit/                       # DevOps Starter Kit documentation & artifacts
    ├── delivery-notes.md              # Flow, Feedback, and Continuous Learning practices
    ├── cloud-model.md                 # Cloud service model selection (PaaS vs IaaS/SaaS)
    ├── regions-azs.md                 # Region selection & Multi-AZ high-availability strategy
    ├── iam-least-privilege.md         # Granular IAM policy for application storage access
    ├── network-topology.png           # Public/Private subnet network architecture diagram
    └── reflection.md                  # Project reflection and scaling roadmap
```

---

## Key Architecture Highlights

### 1. DevOps Delivery Principles
- **Flow:** Accelerating delivery using a standard Git workflow (`main` $ightarrow$ `develop` $ightarrow$ `feature/*`) with small, manageable batch sizes.
- **Feedback:** Early validation using automated PR checks and maintaining architecture-as-code documentation alongside core application files.
- **Learning:** Utilizing feature branches as safe sandboxes for infrastructure experimentation and conducting post-incident/release reflections.

### 2. Cloud Strategy & Reliability
- **Service Model:** **PaaS** (Platform as a Service) chosen for initial rollout to minimize operational overhead and maximize developer velocity.
- **Multi-AZ Redundancy:** Primary deployment spread across two Availability Zones (`AZ-a` and `AZ-b`) with automated load balancing and database replication to eliminate single points of failure.

### 3. Security & Networking
- **Least Privilege IAM:** Custom JSON policy granting strict S3 bucket access (`kijani-app-media-storage`) to the application server without administrative permissions or wildcard resources.
- **Network Segmentation:** VPC design featuring a **Public Subnet** (holding load balancers/ALB and NAT Gateway with IGW routing) and an isolated **Private Subnet** (holding PostgreSQL databases with internal IP routing only).

---

## Git Workflow & Branching Strategy
1. `main` — Production-ready code.
2. `develop` — Active integration branch.
3. `feature/starter-kit-files` — Short-lived working branch merged via Pull Request into `develop`.
