Review inputs:
| Category | Description |
| --- | --- |
| Design purpose | The purpose of this design iteration is to create a design that can support the AIDAP system. |
| Primary functional requirements | UC7 because scalability is an important attribute when choosing a reference architecture. UC8 because the database is a core requirement. UC9 because maintainability is an architectural driver. |
Quality attribute scenarios | Of the seven quality attribute scenarios listed, the three chosen as drivers are: maintainability, as per QA7, RA4, RM1, and RM2, modifiability, per QA4, RM5, R3, and RM1, and interoperability, as per QA5, RD2, R3, RD4, and RD1. |
| Constraints | CON2 and CON3 were chosen because they shape what choice of architecture can be chosen. |
| Concerns | CRN1, CRN5, and CRN7 were chosen as they represent important questions that can be answered by the choice of architecture. |

Iteration goal: Design an architecture for the AIDAP system that can support UC7, UC8, and UC9 while allowing for business logic and UI to be added at a later date.

Major components of the architecture:
| Element | Rationale | Related Quality Attributes |
| --- | --- | --- |
| Database component | To satisfy UC8, a database component that can synchronize with other university systems must be designed. This should be done while complying with RD2 to satisfy interoperability. |
| Cloud-native service component | To satisfy UC7, the system should contain a cloud-native service component so the system can be scaled if needed and maintain a 99.5% monthly availability. |
| Modular AI model | To support continuous deployment, the AI model should be modular so it can be easily replaced or upgraded with zero downtime. |


Choice of reference architecture:
| Design Decision | Rationale |
| --- | --- |
| Structure the system using Web Application reference architecture | The web application reference architecture can be run in a browser and allows for UI and UI process logic, which is pivotal for many requirements and use cases, such as RS9, UC1, UC2, and UC3 to name a few. Complying with RM3 and RM5, the service agents component can be implemented as the AI model for easy modifiability and integration. The Web Application architecture also supports an external database, which is needed for R6. However, one modification that must be made is to add a cache for offline or low connectivity (RS14). |
