# Contingency Project - Epic and JIRA Story Breakdown

## 🧩 EPIC: Contingency UI & Access Control

1. Build Contingency UI for File Upload, Preview, and Enrichment  
2. Build UI using GS Toolkit for Design Consistency  
3. Integrate Authn/Authz with CFT Refstack for Secure Access  
4. Create UAT Plan for Assistant Team Dry Runs  
5. Document End-to-End UI Workflow for Assistant Team  
6. Define UI SLOs for Responsiveness and Upload Preview Latency  

## 🧩 EPIC: API Gateway & Lambda Architecture

7. Set Up API Gateway for Upload and Enrich Endpoints  
8. Develop Upload API Lambda to Handle File Metadata  
9. Develop Enrich API Lambda for TA Format Conversion  
10. Configure CORS and Authentication Policies for APIs  
11. Define Retry Strategy and Standardized Response Codes for API Failures  

## 🧩 EPIC: Cross-Account Integration (AMS DynamoDB)

12. Create IAM Role for Cross-Account Access to AMS DynamoDB  
13. Implement Lookup Integration from Enrich Lambda to AMS DynamoDB  
14. Define Schema and Version Control for Dynamo Lookup Table  

## 🧩 EPIC: Observability & Operational Excellence

15. Add Splunk Alerts for Upload and Enrich Lambda Failures  
16. Build Daily Health-Check Job to Validate Upload and Enrichment Flow  
17. Integrate Slack/Email Alerts for System Failures and Success Heartbeat  
18. Define and Track SLOs for Enrichment Success Rate and Latency  
19. Implement End-to-End Test Automation for File Processing Workflow  

## 🧩 EPIC: File Collection & Scenarios

20. Collect Sample Files – GS Funds Offshore (Mosaic Down Scenario)  
21. Collect Sample Files – GS Funds Onshore (Mosaic Down Scenario)  
22. Collect Sample Files – Non-GS Funds Offshore (Casie Down Scenario)  
23. Collect Sample Files – Non-GS Funds Onshore (SS&C Down Scenario)  
24. Finalize Format Mapping and Edge Cases Across All File Types  

## 🧩 EPIC: Fallback Connectivity – Feasibility

25. Analyze Calastone Connectivity as Fallback for Casie Down (Non-GS Offshore)  
26. Analyze BNY Connectivity as Fallback for SS&C Down (Non-GS Onshore)  
27. Evaluate Feasibility of Using TIP File for Onshore Automation  
28. Propose Automated Upload Route via SFTP/API if Feasible  
29. Document Feature Gaps: Onshore vs Offshore PM Reports  

## 🧩 EPIC: Documentation

30. Document Input/Output File Specifications for Each Fund Type  
31. Create Onboarding Guide for Assistant Team Using Contingency UI  
32. Maintain Version Control and Schema for Dynamo Lookup Table  
33. Build a Master Confluence Page Linking All Components (UI → API → Enrich → Dynamo)  
