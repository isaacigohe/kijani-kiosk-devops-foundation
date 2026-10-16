# KijaniKiosk DevOps Foundation

## Overview
This repository serves as the central engineering repository for the **KijaniKiosk** platform. It captures both the foundational cloud infrastructure designs (Week 2) and the board-ready automated CI/CD pipeline (Week 5).

---

## Repository Structure
```text
kijani-kiosk-devops-foundation/
├── README.md                          # Repository overview and navigation
├── Jenkinsfile                        # Root production-grade Declarative Pipeline
├── starter-kit/                       # Week 2: Infrastructure & Cloud Foundations
│   ├── delivery-notes.md              # Flow, Feedback, and Learning practices
│   ├── cloud-model.md                 # Cloud service model selection (PaaS vs IaaS)
│   ├── regions-azs.md                 # Multi-AZ high-availability strategy
│   ├── iam-least-privilege.md         # S3 least-privilege IAM policy
│   ├── network-topology.png           # Public/Private subnet topology diagram
│   └── reflection.md                  # Week 2 project reflection
└── week5/friday/                      # Week 5: Board-Ready CI Pipeline
    ├── Jenkinsfile                    # Production pipeline copy
    ├── ci-pipeline-board-document.md  # Executive summary for Nia (600-800 words)
    ├── green-pipeline-run.txt         # Full successful build console output
    ├── nexus-versions-screenshot.png  # Nexus registry versioning evidence
    ├── fault-injection-log.md         # Complete 5-stage fault testing matrix
    ├── credential-audit.txt           # Credential hygiene audit evidence
    └── reflection.md                  # Week 5 engineering reflection
```

---

## Key Milestones

### Week 2: DevOps Foundations
- Established Git flow branching strategies (, , ).
- Evaluated cloud service models (PaaS adoption strategy).
- Designed multi-AZ high availability and public/private VPC subnet architecture.

### Week 5: CI Pipeline & Artifact Registry
- Engineered a production-grade Jenkins declarative pipeline pinned to .
- Implemented fast linting before parallel verification (Unit Tests + Security Audit).
- Automated artifact packaging, fingerprinting, and authenticated publishing to Nexus with zero credential leakage.
