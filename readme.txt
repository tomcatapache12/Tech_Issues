|| # || Task Description || Category || Comments / Notes || Owner || Status ||
| 1 | Create Contingency UI | UI | Minimal MVP: Upload file, show preview, trigger conversion, download output | Frontend Dev | ⬜ Not Started |
| 2 | Add support for Authn/Authz using CFT Refstack | Security | Use CFT Refstack for role-based login (assistant team access only) | Infra/Security | ⬜ Not Started |
| 3 | Create API Gateway | Backend / Infra | Expose Upload and Enrich APIs; attach auth + CORS policies | Infra Team | ⬜ Not Started |
| 4 | Create Upload API Lambda | Backend | Parse + store uploaded files (raw + metadata); return upload status | Backend Dev | ⬜ Not Started |
| 5 | Create Enrich API Lambda | Backend | Lookup via Dynamo, enrich, convert to TA-ready format | Backend Dev | ⬜ Not Started |
| 6 | DynamoDB Connectivity with AMS AWS Account | Infra / Integration | Setup cross-account IAM roles and test data access | Infra Team | ⬜ Not Started |
| 7 | [GS Fund] Collect files – Offshore (Mosaic Down) | Data Collection | Use current trading samples; define structure & edge cases | Analyst / QA | ⬜ In Progress |
| 8 | [GS Fund] Collect files – Onshore (Mosaic Down) | Data Collection | Add support for Indian market flows; align with PM report formats | Analyst / QA | ⬜ In Progress |
| 9 | [Non-GS Fund] Collect files – Offshore (Casie Down) | Data Collection | Involve transfer agent variations, file types (XML, Excel, etc.) | Analyst | ⬜ In Progress |
| 10 | [Non-GS Fund] Collect files – Onshore (SS&C Down) | Data Collection | Include both client-initiated and PM-initiated flows | Analyst | ⬜ In Progress |
| 11 | Analyse Calastone connectivity – Casie Down fallback | Feasibility Study | Check if we can auto-upload files via Calastone API | Solution Architect | ⬜ Not Started |
| 12 | Analyse BNY connectivity – SS&C Down fallback | Feasibility Study | Explore API or SFTP-based fallback routes for automation | Solution Architect | ⬜ Not Started |
| 13 | Finalise: Onshore PM report – What's missing for Offshore | Gap Analysis | Identify features not available in offshore trade flow & file structure | Product / BA | ⬜ In Progress |
| 14 | Add Splunk alerts for file upload/enrich failures | Observability | Daily integration-style check that uploads file and validates enrich output to ensure system health | SRE / Dev | ⬜ Not Started |
| 15 | Create UAT plan for assistant team dry runs | UAT / Testing | Prepare scenarios using real data, validate UI flow and conversion logic with assistant team | QA / Product | ⬜ Not Started |
| 16 | Document input/output format specifications | Documentation | For each fund type and scenario (GS/Non-GS, Offshore/Onshore) | Product / Dev | ⬜ Not Started |
| 17 | Set up end-to-end automated test pipeline | Reliability | Mimic real user flow: upload file → enrich → validate → log result to Slack/Splunk | QA / DevOps | ⬜ Not Started |
| 18 | Define SLOs and alert thresholds for contingency flow | Operational Excellence | E.g., Enrichment must complete in <60s, alert if daily volume < expected | Product / SRE | ⬜ Not Started |
