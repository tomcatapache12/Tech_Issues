
QA and UAT Strategy
1. Test Objective
Ensure that:

Input files are correctly parsed.

Business rules/logic are applied correctly.

Output files are in the correct format and accurate.

The system behaves reliably under failure or bypass scenarios.

It aligns with user expectations and operational workflows.

2. QA (Quality Assurance) Phase
🧷 Scope:
Functional testing

Negative testing

File validation and parsing logic

Output file generation (format, structure, content)

Exception handling (bad data, missing fields, duplicates)

Logging, alerts, and error reporting

Security (file access control, encryption if needed)

🧪 QA Test Scenarios:
Valid Input File

Verify processing of correctly formatted file.

Validate output files for all supported brokers.

Invalid Input File

Corrupt format, missing fields, invalid trade details.

System should reject with proper error messages.

Partial Valid Data

Some rows correct, some incorrect. Test handling logic.

Large File Handling

Performance and memory management.

File Naming Convention

Correct file names based on broker/trade IDs.

Output Accuracy

Verify calculations, mappings, and data transformations.

Bypass Verification

Ensure Mosaic is not called or invoked anywhere.

Audit Logging

Logs capture upload, processing status, errors.

Role-Based Access

Only authorized users can use contingency path.

Recovery Scenarios

What happens if upload fails mid-way?

✅ Tools (if applicable):
Automation (for regression and smoke tests)

Mock services (to simulate broker systems or outputs)

3. UAT (User Acceptance Testing) Phase
🎯 Goal:
Ensure that the solution meets business expectations under real-world use cases.

👥 UAT Users:
Ops team or trading support users

End users responsible for file uploads and broker communication

🎯 Key UAT Objectives:
Validate that the correct files are generated per real trade scenarios.

Ensure workflows are user-friendly and efficient under pressure.

Confirm error handling is understandable and actionable.

Test how the team can operate without Mosaic (as a fallback).

Validate turnaround time and usability during a crisis.

UAT Plan:
Test Cases Aligned to Business Scenarios

Day-to-day use cases

Peak trading day fallback

Manual file editing/upload edge cases

Dry Run / Simulation

Simulate Mosaic failure and walk through the full contingency process.

Sign-Off Criteria

Business confirms output is usable as-is for broker submission.

No blockers, and user confidence is established.

📅 Proposed Timeline
Phase	Activities	Duration
QA Prep	Test case writing, environment setup	2-3 days
QA Execution	Run test cases, fix bugs	5-7 days
QA Sign-Off	Regression + Go/No-Go decision	1-2 days
UAT Prep	Real trade files, user training	1 day
UAT Execution	Run real scenarios, feedback collection	3-5 days
UAT Sign-Off	Final approval by business users	1 day

🧩 Dependencies
Test data (realistic trade files)

Output file specification from brokers

Environment isolated from Mosaic

Clear fallback trigger (how to enter contingency mode)

✅ Deliverables
QA Test Plan & Results

Defect Logs

UAT Scripts

UAT Sign-off Document

