**ADD Iteration 2 -- AIDAP System**
----------------------------------

### **Step 1: Review Inputs**

| **Category** | **Details** |
| --- | --- |
| **Design Purpose** | This is the second iteration of a greenfield architecture for the AIDAP system. The purpose is to refine the architecture to better support secure access to academic data and high system availability under institutional workloads. |
| **Primary Functional Requirements (from Use Cases)** | **UC5 -- Student Authentication:** Students (and staff) must log in through institutional SSO to access AIDAP via web/mobile/voice. The system must protect student-specific data.\
**UC1 -- Asking an Academic Question:** Users query grades, deadlines, etc., using natural language; AI must access sensitive academic data securely.\
**UC2 -- Receiving Notifications:** Personalized notifications must be delivered only to the correct, authenticated user.\
**UC4 -- Viewing Class Analytics:** Only authorized instructors can view course analytics. |
| **Quality Attributes (Drivers for this iteration)** | **Security:** Must detect and block brute-force login attempts, prevent unauthorized access to data, and log security events within 500ms (R8, RS8, RS7, RA5).\
**Availability:** During failures, the system must perform automatic failover and maintain 99.5% monthly availability (RS11, RA6, R7). |
| **Constraints** | **CON-1:** Support up to 5,000 concurrent users with acceptable response time (RS10, RA7).\
**CON-2:** Available on mobile, web, and voice-assistant devices (RS9).\
**CON-3:** Must integrate with university systems via standard APIs (RD1, RD2).\
**CON-5:** Must adhere to institutional security/privacy regulations for personal data (R8, RA5). |
