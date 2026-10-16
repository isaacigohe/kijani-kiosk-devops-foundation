# Week 5 CI Pipeline Project Reflection

## 1. Requirement Tension & Prioritisation
During this week's pipeline implementation, a clear tension emerged between **rapid feedback (developer speed)** and **exhaustive validation (security & reliability)**. Specifically, running security audits alongside full test suites in a single sequential stage added significant runtime delay to every commit. To resolve this without sacrificing security, I prioritized engineering flow by placing **Linting first** as a ultra-fast fail-fast gate, and executing **Test and Security Audit in parallel** within a unified `Verify` stage.

## 2. Technical vs. Non-Technical Translation
* **Board Document Version (Non-Technical):** "In a financial services platform, delivering broken functionality or security risks is unacceptable; our automated pipeline operates under a strict rule that if any single check detects an anomaly, the entire delivery process halts instantly."
* **Technical Version:** "The Jenkins pipeline implements fail-fast declarative semantics where non-zero exit codes in any stage trigger an immediate pipeline abort, bypassing downstream stages and invoking post-failure cleanup handlers."
* **Comparison:** Both versions convey the identical guarantee: flawed code is blocked from progressing. The non-technical version focuses on **business risk mitigation**, whereas the technical version describes **execution semantics and exit code handling**.

## 3. Scaling Bottleneck & Architecture Evolution
If KijaniKiosk grows from 4 to 40 developers, the single part of the pipeline that would break first is the **single shared Jenkins VM agent execution model**. Concurrent PRs would queue rapidly behind `disableConcurrentBuilds()`, creating delivery bottlenecks. To scale, we would transition from a single VM agent to **ephemeral Kubernetes-based dynamic build agents**, allowing each build to run in an isolated, auto-scaled pod concurrently.
