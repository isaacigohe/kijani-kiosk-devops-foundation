# KijaniKiosk Region and Multi-AZ Architecture

## Region Selection Strategy

### Primary Region Choice
- **Primary Region:** `eu-central-1` (Frankfurt) or `us-east-1` (N. Virginia), selected based on proximity to primary users to minimize network latency and meet data residency/compliance requirements.

---

## Multi-Availability Zone (Multi-AZ) Reliability Strategy

### What is an Availability Zone (AZ)?
An Availability Zone consists of one or more isolated data centers with independent power, cooling, and networking within a region.

### High Availability and Fault Tolerance Logic
- **Redundancy:** Applications and database instances are deployed across at least **two distinct Availability Zones** (e.g., `AZ-a` and `AZ-b`).
- **Automatic Failover:** If an infrastructure outage affects `AZ-a`, traffic is automatically rerouted by the Load Balancer to `AZ-b` without service disruption.
- **Database Replication:** The database uses a Primary-Standby setup across multi-AZs with synchronous/asynchronous replication to prevent data loss.

---

## Summary
Designing with multi-AZ redundancy from day one ensures high availability (99.99% uptime) and prevents single points of failure across physical data centers.
