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

Instantiate elements:
| Design Decision | Rationale |
| --- | --- |
| Develop AI model as a service in data layer | By developing the AI model as a service, the component can stay modular and easily updated or modified when needed. |
| Add a local database in data layer | To satisfy RS14, a local database should be implemented for periods of zero to low connectivity. |

Model diagram:

<img width="338" height="627" alt="image" src="https://github.com/OTUSOFE365025/project-group-30-crn-45740/blob/phase2/model.PNG" />

Analysis of design:
| Not Addressed | Partially Addressed | Completely Addressed | Rationale |
| --- | --- | --- | --- |
|  | UC1 |  | The AI model implementation has been decided, but the UI has not been. |
| UC2 |  |  | The UI implementation has not yet been decided. |
| UC3 |  |  | The UI implementation has not yet been decided. |
|  | UC4 |  | The architecture to facilitate this use case has been decided, but the UI has not been. |
| UC5 |  |  | The system security has not yet been decided. |
| UC6 |  |  | The UI implementation has not yet been decided. |
|  |  | UC7 | The cloud-native service that can support 99.5% availability and a high load has been decided. |
|  |  | UC8 | The databases to support data synchronization, offline modes, and providing knowledge for the AI model has been identified. |
|  |  | UC9 | The cloud-native service to support continuous deployment and no downtime has been decided. |
|  | QA1 |  | The AI and scalability implementations have been decided, but not UI. |
| QA2 |  |  | The UI implementation has not yet been decided. |
|  |  | QA3 | The cloud-native service that can support 99.5% availability and a high load has been decided. |
|  |  | QA4 | The data layer and databases have been designed to be modular so changes can be made quickly without affecting other parts of the system.  |
|  | QA5 |  | The decision to implement standard APIs for the databases has been made. |
| QA6 |  |  | No decision regarding security has been made. |
| QA7 |  |  | The cloud-native service that can support continuous deployment and zero downtime has been made. |
|  | CON1 |  | The cloud-native service that can support scalability has been made, but decisions regarding performance has not. |
|  |  | CON2 | The architecture to support mobile, web, and voice-assistant devices has been decided. |
|  |  | CON3 | The decision to implement standard APIs for the databases has been made. |
|  |  | CON4 | The addition of a local database in the data layer has been decided. |
| CON5 |  |  | No decision regarding security has been made. |
| CRN1 |  |  | No decision regarding security and user authentication has been made. |
| CRN2 |  |  | No decision regarding security and user data has been made. |
| CRN3 |  |  | No decision regarding UI has been made. |
| CRN4 |  |  | No decision regarding UI has been made. |
|  |  | CRN5 | Analytics will be exposed to system maintainers and administrators. |
| CRN6 |  |  | No decision regarding UI has been made. |
|  |  | CRN7 | The AI will be implemented as a service in service helper in the data layer. |
