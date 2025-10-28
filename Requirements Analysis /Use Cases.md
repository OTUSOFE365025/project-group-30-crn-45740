Add the Use Cases to this file


| Use Case | Description | Related Requirements |
|---|---|---|
| UC1-Asking an Academic Question | Students should be able to ask academic questions such as “What did I receive on SOFE3650 midterm?”, “What's the deadline for SOFE3650 phase one?”. The AI system must be able to interpret queries using natural language processing to answer questions | R1, R5, RS1, RS10 |
| UC2-Recieving Notifications | The system must push notifications to students about schedule changes, upcoming assignment deadlines, and lecturer announcements. Lecturers should also receive notifications from students for any inquiries. The notifications should be personalized for each user and can be customized, and should only be seen by said user. | R6, RS2, RS6, RS8 |
| UC3-Posting Course Announcements | Lecturers are able to post course announcements either using voice or text commands. The system should only allow the authorized lecturer for a given course to modify course data. | R1,RL2,RL8 |
| UC4-Viewing Class Analytics | Lecturers are able to access the dashboard or query the system to return a summarized class analytics of all students for a given course. The system must generate a complete response using live and stored data and ensure that it only returns analytics for authorized lecturers for the given course. | R6,RL3,RL8,R8 |
| UC5-Student Authentication | Students can access the AIDAP via mobile or web-app and must be prompted for authentication using the institution’s single sign-on. The system must also protect student-specific data. | R8,RS7,RS8 |
| UC6-Interpreting Natural Language | All users can input in natural language to the system, and it should be able to interpret the query and learn from previous conversations to improve future responses. | R1,R5,R6,RS4,RS5 |
| UC7-Availability and Scalability | The system will be operating under a high load, with thousands of users in an institution. The system can scale and maintain a 99.5% monthly availability and provide automatic failover and backup recovery. | R7,R11,RA7,RA6 |
| UC8-Data Synchronization with Systems | The system must synchronize data with connected university systems like the LMS or registration database. This is done at configurable intervals, and the system must maintain data integrity and consistency across all systems. | R3, RD1, RD4 |
| UC9-Uploading New System Updates | System Maintainers should be able to release system updates, new features, and upgraded AI models with zero downtime for end-users. | RM1, RM2, RM7 |


<img width="583" height="526" alt="image" src="https://github.com/user-attachments/assets/c95da21b-0a8e-4652-8b6c-35648dc286cb" />
