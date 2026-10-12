# KijaniKiosk DevOps Delivery Notes

## Overview
This document outlines how the Three Ways of DevOps—**Flow**, **Feedback**, and **Continuous Learning**—are applied to the engineering delivery pipeline at KijaniKiosk.

---

## 1. The First Way: Flow (Accelerating Delivery)
To optimize the flow of work from development to production, KijaniKiosk uses a structured Git workflow:

- **Branching Strategy:** 
  - `main`: Represents production-ready code.
  - `develop`: Acts as the integration branch for upcoming features.
  - `feature/*`: Short-lived isolation branches for individual tasks or fixes.
- **Small Batch Sizes:** Work is broken down into granular deliverables (e.g., individual starter-kit modules) to reduce merge friction and cycle time.
- **Pull Requests (PRs):** Changes move from `feature/*` to `develop` via mandatory pull requests to prevent broken code from blocking the pipeline.

---

## 2. The Second Way: Feedback (Amplifying Feedback Loops)
Feedback mechanisms ensure issues are caught early before reaching production:

- **Automated PR Reviews:** Automated status checks and reviewer code reviews validate infrastructure designs and configurations before merging into `develop`.
- **Infrastructure Visibility:** By maintaining infrastructure documentation directly alongside code in the `starter-kit/` directory, all team members gain early visibility into cloud and network architectural decisions.
- **Fast Iteration:** Shorter feedback loops allow engineers to address configuration issues within minutes rather than during late-stage deployment.

---

## 3. The Third Way: Continuous Learning & Experimentation
Cultivating a culture of continuous learning enables long-term system resilience:

- **Safe Architectural Sandbox:** Isolating changes inside feature branches encourages team members to experiment with IAM policies and subnet designs without risking live environments.
- **Post-Mortems & Reflections:** Every release cycle concludes with structured reflections to identify shortcuts taken, key design trade-offs, and future scalability improvements.
- **Knowledge Sharing:** Infrastructure files are maintained as clear Markdown documentation so new engineers can quickly onboard and learn system architecture.
