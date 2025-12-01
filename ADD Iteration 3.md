Iteration goal: Refine the system design to ensure QA5, QA6, and QA7 are satisfied, because these quality attributes have not yet been completely addressed by the design.

---

Major components of the architecture:
| Element | Rationale | Related Quality Attributes |
| --- | --- | --- |
| File integrity verification | To satisfy QA5, a component that verifies file integrity of packets sent between all connected systems to ensure 100% data integrity must be implemented in the system. | QA5 |
| Live monitoring dashboard | Allow system maintainers to monitor the general health of the system, notifying system maintainers when failures may occur. | QA6 |
| Network traffic analyzer | To protect the system from potential DDoS attacks to ensure the health of the system, the component must be able to analyze large amounts of network traffic to assess and block traffic if an attack is detected. | QA7 |

---

Choice of reference architecture:
| Design Decision | Rationale |
| --- | --- |
| Extend current Web Application reference architecture with new components. | Keep the reference architecture the same but add three new components to support QA-5, QA-6, and QA-7, ensuring they are modular so they can be easily modified if needed. |

---

Instantiate elements:
| Design Decision | Rationale |
| --- | --- |
| File integrity verification service | Supports QA5 by verifying the integrity of packets sent between systems and ensuring 100% data integrity. |
| Live health, latency, and error dashboards | Supports QA7 by allowing maintainers to monitor the general health of the system at any given time. |
| Network traffic analyzer | Supports QA6 by preventing mitigating DDoS attacks on the system by analyzing network traffic and IP addresses, retrieving known malicious IPs from a database. |

---
