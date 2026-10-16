# KijaniKiosk CI Pipeline Fault Injection Log

| Faulted Stage | Injected Fault | Observed Downstream Behaviour | Design Rationale |
| :--- | :--- | :--- | :--- |
| **Lint** | Injected syntax error in source file | Pipeline halted immediately; Build, Verify, Archive, and Publish stages were skipped. | Failing fast on simple formatting/syntax errors prevents wasting computing resources on longer build and test phases. |
| **Build** | Invalid build configuration command () | Pipeline halted at Build stage; Verify, Archive, and Publish stages were skipped. | Downstream tests and artifact publication cannot execute if compiled application assets fail to assemble. |
| **Verify (Test / Security Audit)** | Introduced failing unit test () | Parallel Verify stage marked as FAILED; Archive and Publish stages were skipped;  executed in . | Unvalidated or failing code must never be packaged or distributed to registry storage. |
| **Archive** | Missing target artifact path () | Pipeline failed at Archive stage; Publish stage was skipped. | A release cannot proceed to publishing if the generated build output is missing or corrupt. |
| **Publish** | Invalid Nexus URL / Network timeout | Pipeline failed during Publish step;  executed cleanup to remove temporary . | Failed registry deployments must immediately halt the pipeline and clean up ephemeral auth credentials. |

---
**Recovery Confirmation:** All faults were systematically resolved and the pipeline was returned to a verified green status following each fault test.
