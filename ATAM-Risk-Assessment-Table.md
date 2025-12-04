| Risk ID | Quality Attribute | Scenario | Sensitivity Point | Trade-Off Point | Risk Description |
|--------|-------------------|----------------------------------|-------------------|-----------------|------------------|
| R-P1 | Performance | ~2000 concurrent students submit complex queries → AI Core must return contextual results within 2 seconds on average. | AI model size, inference strategy (sync vs async), live data aggregation. | Accuracy vs Response Time | If the AI model or real-time aggregation is too computationally expensive, the 2-second response requirement may be violated under normal academic load. |
| R-U1 | Usability | Student changes notification & language preferences on mobile with limited network → 90% complete without help. | UI workflow complexity, number of API round-trips, mobile optimization. | Feature Richness vs Ease of Use | Multi-step workflows or heavy network calls may cause users on slow networks to fail the task, violating usability targets. |
| R-A1 | Availability | During peak load, a critical DB connection fails → system must perform invisible automatic failover and still meet 99.5% availability. | Single vs multi-region deployment, replication strategy, failover orchestration. | Availability vs Cost | If failover is not fully automated or redundancy is limited, even short outages can violate the availability requirement. |
| R-M1 | Modifiability | Maintainer integrates a new Student Evaluation System and deploys in < 5 working days. | Coupling between Core Services and Data Integration Layer, use of standard adapters. | Development Speed vs Architectural Decoupling | Tight coupling across services may require widespread code changes, making the 5-day integration target unrealistic. |
| R-I1 | Interoperability | System receives large LMS updates → must ensure 100% data consistency across systems. | Synchronization frequency, transaction boundaries, conflict-resolution policy. | Consistency vs Throughput | High-volume updates can cause partial sync or stale records if consistency mechanisms are insufficient. |
| R-S1 | Security | Brute-force attack on admin accounts → system must detect, block, and log the event within 500 ms. | Authentication throttling rules, intrusion-detection latency, logging pipeline speed. | Security Strictness vs Performance | If detection or synchronous logging is slow under load, the 500 ms security response requirement may be violated. |
| R-MA1 | Maintainability | Continuous deployment with zero downtime while live dashboards monitor health & latency. | Observability architecture, deployment strategy (blue-green/canary). | Monitoring Depth vs Runtime Overhead | Insufficient telemetry delays failure detection; excessive telemetry degrades system performance. |

### Key Architectural Risks
- Performance risk from AI inference and live data aggregation.
- Availability risk from incomplete or slow failover automation.
- Security risk from delayed brute-force attack detection and logging.
- Interoperability risk from large LMS synchronization bursts.
- Modifiability risk from tight coupling in the Data Integration Layer.
- Usability risk from mobile network constraints.
- Maintainability risk from weak observability.

### Non-Risks (Architectural Strengths)
- SSO-based authentication and centralized identity management.
- Automated CI/CD deployment pipelines.
- Dedicated Data Integration Layer for external systems.
- Cloud-based infrastructure supporting replication.
- Live monitoring dashboards for operations.

### Sensitivity Points
- AI model selection and inference mode.
- Database replication and failover configuration.
- Authentication throttling and intrusion detection latency.
- LMS data synchronization strategy.
- Coupling between integration and core services.
- Telemetry and logging pipeline design.

### Trade-Off Points
- Accuracy vs Performance
- Availability vs Cost
- Security vs Runtime Performance
- Consistency vs Throughput
- Usability vs Feature Complexity
- Monitoring Detail vs System Overhead
