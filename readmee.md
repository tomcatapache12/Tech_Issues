
## Objective:
👉 Build a scalable and resilient **Contingency Framework** for Mosaic Trading to ensure seamless trade processing when the primary Mosaic portal is down.

| **Key Result** | **Task** | **Outcome** | **Target Date** | **Status** |
|-------------- |----------|------------|----------------|------------|
| **KR1: Design and Develop a Cloud-Based Contingency Framework** | Design cloud-based architecture for contingency framework | Approved design document | [Target Date] | [Pending/In Progress/Completed] |
| | Analyze and prepare document for network connectivity between GSInet and AWS Cloud | Successful connectivity established with <1% failure rate | [Target Date] | [Pending/In Progress/Completed] |
| | Implement authentication and authorization (SSO, MFA) | Secure login and access control for SS team | [Target Date] | [Pending/In Progress/Completed] |
| | Define scalability limits and expected load for contingency usage | Defined capacity and load-handling document | [Target Date] | [Pending/In Progress/Completed] |
| **KR2: Build Contingency UI for Trade Inbound** | Build file upload screen with basic validation (e.g., duplicate entry) | File upload functionality with >99% success rate | [Target Date] | [Pending/In Progress/Completed] |
| | Build secure login screen | Successful login for authorized users | [Target Date] | [Pending/In Progress/Completed] |
| | Establish GitLab/CFT pipeline for React app deployment to AWS S3 | Automated deployment pipeline established | [Target Date] | [Pending/In Progress/Completed] |
| | Handle large file sizes and concurrent uploads | Successful upload of files up to defined size limit with no performance issues | [Target Date] | [Pending/In Progress/Completed] |
| **KR3: Enable Trade Outbound Handling for GS and Non-GS Funds** | Define contract for converting input files to Casie format | Approved contract document | [Target Date] | [Pending/In Progress/Completed] |
| | Explore plugging Non-GS funds into Calastone if Casie is down | Document feasibility report | [Target Date] | [Pending/In Progress/Completed] |
| | Define contract for converting input files to Calastone format | Approved contract document | [Target Date] | [Pending/In Progress/Completed] |
| | Handle trade outbound failures with retry or alternate path | Successful retry or alternate execution path defined | [Target Date] | [Pending/In Progress/Completed] |
| **KR4: Ensure Successful Trade Acknowledgment Handling** | Leverage existing TA inbound acknowledgment handling | Successful ACK reception and processing | [Target Date] | [Pending/In Progress/Completed] |
| | Ensure end-to-end monitoring and logging for outbound trades | Full visibility into outbound trade status in real-time | [Target Date] | [Pending/In Progress/Completed] |
| **KR5: Ensure Operational Readiness and Monitoring** | Set up monitoring and alerting (CloudWatch, Grafana, Prometheus) | Real-time monitoring and alerts established | [Target Date] | [Pending/In Progress/Completed] |
| | Define and test rollback strategy for contingency deployment | Approved rollback plan | [Target Date] | [Pending/In Progress/Completed] |
| | Conduct end-to-end DR testing for contingency framework | DR test execution with >95% success rate | [Target Date] | [Pending/In Progress/Completed] |
| | Prepare and deliver training to SS Team for contingency handling | SS Team trained and confident to handle contingency cases | [Target Date] | [Pending/In Progress/Completed] |
