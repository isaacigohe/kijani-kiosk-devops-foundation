# KijaniKiosk Cloud Service Model Evaluation

## Selected Service Model: Platform as a Service (PaaS)

For the initial engineering foundations of KijaniKiosk, **PaaS (Platform as a Service)** is the recommended cloud delivery model (e.g., AWS Elastic Beanstalk, Heroku, or GCP App Engine).

---

## Justification and Comparison

### 1. PaaS (Chosen Model)
- **Focus on Core Product:** PaaS abstracts away underlying server management, OS patching, and raw network configuration, allowing the engineering team to focus entirely on application code.
- **Faster Time to Market:** Built-in auto-scaling and managed runtime environments accelerate initial deployment before customer traffic grows significantly.
- **Lower Operational Overhead:** Reduces the need for dedicated 24/7 infrastructure management in the early stage.

### 2. Infrastructure as a Service (IaaS) — Why Not Now?
- Requires full management of OS updates, security patching, and virtual machine provisioning.
- Introduces unnecessary operational complexity for early-stage architecture.
- *Future Transition:* As KijaniKiosk scales and requires custom OS-level tuning or complex microservices, migrating to IaaS (e.g., AWS EC2, Kubernetes) will make sense.

### 3. Software as a Service (SaaS) — Why Not Now?
- Ready-made software offers no customization or control over KijaniKiosk's core business logic and database layer.

---

## Conclusion
PaaS provides the optimal balance of developer velocity, low maintenance overhead, and scalability during KijaniKiosk's foundational phase.
