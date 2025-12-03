Iteration goal: Refine the system design to ensure QA5, QA6, and QA7 are satisfied, because these quality attributes have not yet been completely addressed by the design.

---

Major components of the architecture:
| Element | Rationale | Related Quality Attributes |
| --- | --- | --- |
| File integrity verification | To satisfy QA5, a component that verifies file integrity of packets sent between all connected systems to ensure 100% data integrity must be implemented in the system. | QA5 |
| Live monitoring dashboard | Allow system maintainers to monitor the general health of the system, notifying system maintainers when failures may occur. | QA7 |
| Multi-factor authentication | To protect the system from potential brute force login attacks, the component must allow users to set up multi-factor authentication through their phone using a one-time password. | QA6 |

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
| Multi-factor authentication | Supports QA6 by preventing malicious actors from brute forcing their way into a user's account. |

---

Diagram:

<img width="865" height="643" alt="image" src="iteration3_diagram.PNG" />

---

Analysis of Design:
| Not Addressed | Partially Addressed | Completely Addressed | Rationale |
| --- | --- | --- | --- |
|  |  | UC3, UC4 | UC3 and UC4 are faciliated by the file integrity verification service, ensuring that all messages that go towards analytics and notifications have 100% data integrity. |
|  |  | QA5, QA6, QA7 | Components to enchance interoperability, security, and maintainability have been implemented in the design. |
|  |  | CON3, CON5 | The new components are connected to the API gateway and the MFA adheres to security regulations |
|  |  | CRN1 | MFA addresses how users will authenticate. |
