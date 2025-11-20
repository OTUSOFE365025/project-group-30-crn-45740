## Iteration 2 – ADD

### Review inputs:

| Category | Description |
| --- | --- |
| Design purpose | Design the UI and application/service layer for AIDAP so users can securely interact with the system via web, mobile, and receive personalized notifications. |
| Primary functional requirements | UC1 (asking academic questions) and UC6 (interpreting natural language) because they define the core conversational flow. UC2 (receiving notifications) because it drives the notification pipeline. UC5 (student authentication) because secure access is required before exposing user-specific data. |
| Quality attribute scenarios | Performance: responses within 2 seconds under normal load (CON1). Usability: students can intuitively manage notification and language preferences (RS6). Security: SSO and role-based access prevent unauthorized access and detect login abuse. |
| Constraints | CON1 (up to 5,000 concurrent users with ~2s response), CON2 (support web, mobile), and CON5 (adhere to institutional security and privacy regulations). |
| Concerns | CRN1 (identity and access), CRN2 (privacy and compliance), CRN3 (notifications), CRN4 (UI/UX), and CRN6 (content and announcement workflow). |

---

### Iteration goal:

Design an architecture for the **presentation and application/service layers** that supports UC1, UC2, UC5, and UC6 using the existing web application reference architecture.

---

### Major components of the architecture:

| Element | Rationale | Related Quality Attributes |
| --- | --- | --- |
| Web & Mobile UI Clients | Provide conversational UI and dashboards for students and lecturers, and allow users to manage preferences (language and notifications) on different devices. | Usability, Performance |
| API Gateway / Conversation API | Single entry point for all clients; centralizes auth, rate limiting, logging, and routing to backend services to meet performance and security goals. | Performance, Security, Maintainability |
| Conversation Service & AI Orchestrator | Handle conversational state and route queries to the AI model and data sources, enabling UC1 and UC6 without exposing data-layer details. | Performance, Modifiability |
| Auth & RBAC Service | Integrates with institutional SSO and enforces roles (student/lecturer/admin/maintainer) at the service boundary to protect user data. | Security |
| Notification & Preferences Services | Manage subscriptions, channels, and user preferences so notifications are timely, personalized, and configurable. | Usability, Performance, Security |

---

### Choice of reference architecture:

| Design Decision | Rationale |
| --- | --- |
| Extend the existing Web Application reference architecture with an API Gateway and a set of backend application services | Keeps the browser-based model from Iteration 1 while adding a clear separation between clients, API Gateway, and application services. This supports multi-channel access (web, mobile), allows centralized security and performance control, and keeps conversation, auth, and notification logic modular and replaceable. |

---

### Instantiate elements:
| Design Decision | Rationale |
| --- | --- |
| Split the client tier into Web UI and Mobile UI | Supports CON2 and allows each client to optimize its UI/UX without changing backend logic. |
| Introduce a centralized API Gateway | Improves security through token validation, rate limiting, and uniform request handling; supports performance goals. |
| Add Auth & RBAC Service | Ensures secure SSO-based authentication and enforces permissions for accessing academic data. |
| Add Conversation, Notification, and Preferences Services | Makes core flows (UC1, UC2, UC6) modular and easier to evolve while keeping the architecture clean and maintainable. |

---

### Model diagram:

![Iteration 2 Architecture Diagram](phase2/ADD_iteration_2_diagram.drawio.png)


---

### Analysis of design:

| Not Addressed | Partially Addressed | Completely Addressed | Rationale |
| --- | --- | --- | --- |
|  | UC3, UC4 | UC1, UC2, UC5, UC6 | UC1/UC2/UC5/UC6 have end-to-end paths defined through the UI, API Gateway, and services. UC3 (announcements) and UC4 (analytics) have places in the architecture (Conversation, Notification, Analytics services) but detailed workflows and UIs will be refined later. |
|  | Performance QA, Usability QA, Security QA |  | Tactics for performance (gateway, concurrency), usability (separate UIs and preferences), and security (Auth & RBAC, SSO, gateway validation) are in place, but low-level tuning and policy details are left for later iterations. |
|  | CON1, CON5 | CON2 | Multi-channel access (web, mobile) is fully supported by the separated clients and shared API. Performance and security constraints are architecturally considered but need implementation and configuration to be fully satisfied. |
|  | CRN2, CRN4, CRN6 | CRN1, CRN3 | Identity and access (CRN1) and notifications (CRN3) have dedicated services and clear responsibilities. Privacy, UX consistency, and detailed announcement workflows are partly addressed but will be completed when UI screens, retention rules, and content flows are fully designed. |
