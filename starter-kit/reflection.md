# KijaniKiosk DevOps Project Reflection

## 1. Where were you tempted to take shortcuts?
I was tempted to use overly broad wildcard permissions (`"Resource": "*"`) in the IAM policy to save time configuring granular bucket ARNs. I also considered skipping multi-AZ planning to simplify the initial network design.

## 2. Which architectural decision required the most reasoning?
Choosing between IaaS and PaaS required the most careful thought. While IaaS offers maximum control, PaaS was chosen to prioritize engineering flow and fast feedback loops during KijaniKiosk's early growth stage.

## 3. If the KijaniKiosk platform grows significantly, what would you improve first?
1. **Containerization & Orchestration:** Transition from PaaS to Kubernetes (EKS) for fine-grained container orchestration.
2. **Infrastructure as Code (IaC):** Automate all cloud provisioning using Terraform or AWS CloudFormation.
3. **CI/CD Pipeline:** Implement fully automated testing, linting, and deployment pipelines triggered on Git merges.
