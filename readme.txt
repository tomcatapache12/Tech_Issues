Title: Mosaic Contingency Platform – Delivery Plan
1. Overview
The Mosaic platform facilitates high-stakes B2B trading across multiple channels:

File-based – Trades submitted via SFTP/Email.
Mosaic UI (Portal) – Trades placed directly through the Mosaic interface.
API-based – Trades submitted via direct API calls.
Queue-based – Trades submitted through message queues (e.g., IBM MQ).
Currently, we are addressing the scenario where Mosaic UI is down. This impacts high-value trades for both offshore and onshore funds.

Scope (Initial):
✅ Offshore funds – Requirements and flow are defined.
🔍 Onshore funds – Requirements need to be identified (marked as TODO).

2. Scope
Phase 1:

Build a contingency platform for offshore fund processing.
Automate trade detail collection and conversion to Cashew-compatible format.
Phase 2:

Identify and define the flow for onshore funds.
Expand contingency platform support for onshore scenarios.
Future Expansion:

Adapt platform to support contingency for file-based, API-based, and queue-based trade placements.
Build modular components to handle future scenarios without reworking the platform.
3. Offshore Cases
Mosaic UI down, Casie up:

Assistant team receives trade details via phone or email.
Details are collected in a spreadsheet.
Contingency platform validates and converts data to Cashew-compatible format.
File is uploaded to Cashew via Calastone.
Casie down, Calastone up:

Assistant team receives trade details via phone or email.
Details are collected in a spreadsheet.
Contingency platform validates and converts data.
Platform temporarily stores data until Casie is restored OR
Bypass Casie and directly upload the file to Calastone (if supported).
4. Objectives
✅ Automate manual trade processing during Mosaic UI outage.
✅ Ensure data consistency and validation for offshore funds.
✅ Provide a flexible framework for future contingency cases.
✅ Support scalability across different trade channels.

5. Technical Plan
Frontend:

Build a UI with file upload (CSV, Excel).
Preview and validate data before submission.
Display upload status and error handling.
Backend:

Create a REST API for file processing.
Parse uploaded files and map data fields.
Convert data to Cashew-compatible format.
Generate a downloadable output file.
Data Handling:

Offshore funds:
Case 1: Mosaic → Casie → Calastone → Outside fund connectivity.
Case 2: Bypass Casie if down → Directly upload to Calastone (if supported).
Onshore funds: Define the flow, connectivity, and format requirements in Phase 2.
Security:

Implement role-based access control (RBAC).
Encrypt uploaded files and processed data.
Future Flexibility:

Add support for file-based, API-based, and queue-based input in future phases.
Build configurable data mapping for different trade formats.
6. Deliverables
Deliverable	Owner	Deadline	Status
Frontend UI (Upload & Preview)	Developer 1	YYYY-MM-DD	Not Started
Backend API (File Processing)	Developer 2	YYYY-MM-DD	Not Started
Offshore Funds Data Mapping	Developer 2	YYYY-MM-DD	Not Started
Onshore Funds Flow Definition	Lead	YYYY-MM-DD	TODO
Testing and QA	Lead + Developers	YYYY-MM-DD	Not Started
Documentation	Lead	YYYY-MM-DD	Not Started
7. Risks & Mitigations
Risk	Impact	Mitigation
Offshore and Onshore format mismatch	High	Create a flexible mapping strategy
Large file size upload	Medium	Implement file size limits and chunked processing
Data validation failure	High	Provide clear error messages and allow retry
Onshore flow definition delay	Medium	Engage stakeholders early to define requirements
Expansion to new trade channels (e.g., API)	Medium	Design the platform with a plug-and-play architecture
8. Dependencies
Cashew format specifications from the transfer agent.
Mosaic database schema access for data validation.
Offshore and onshore fund data structure clarity.
Stakeholder input to define onshore flow.
9. Timeline
Milestone	Date	Status
Start Development	YYYY-MM-DD	Not Started
Frontend and Backend Integration	YYYY-MM-DD	Not Started
Offshore Fund Processing	YYYY-MM-DD	Not Started
Onshore Flow Definition	YYYY-MM-DD	TODO
Initial Testing	YYYY-MM-DD	Not Started
Final Testing and QA	YYYY-MM-DD	Not Started
Go Live	YYYY-MM-DD	Not Started
