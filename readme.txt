EPIC: Contingency UI & Access Control
|| Story || Comments ||
| Create Contingency UI (MVP) | File upload, preview, enrichment trigger, result download |
| Add support for Authn/Authz using CFT Refstack | Limit access to assistant team; leverage existing RBAC |
| Create UAT plan for assistant team dry runs | Real data + guided flows |
| Document UI flow & expected user actions | For onboarding assistant team |
| Define SLOs for UI responsiveness | e.g., UI should respond under 2s for file upload preview |

🧩 EPIC: API Gateway & Lambda Architecture
|| Story || Comments ||
| Create API Gateway | Expose upload + enrich endpoints |
| Create Upload API Lambda | Stores uploaded file and metadata |
| Create Enrich API Lambda | Converts file to TA format using Dynamo lookup |
| Set up CORS/Auth policies for APIs | For UI integration |
| Define retry strategy or response codes | Even though fallback is none, logging must be clear |

🧩 EPIC: Cross-Account Integration (AMS DynamoDB)
|| Story || Comments ||
| Configure IAM role for cross-account access | Between Mosaic Contingency and AMS |
| Test lookup integration from Enrich Lambda | Validate fund mapping, TA formats |
| Define schema and version control for Dynamo entries | So format changes are manageable |

🧩 EPIC: Observability & Operational Excellence
|| Story || Comments ||
| Add Splunk alerts for file upload/enrich failures | Core integration health |
| Build health-check job (integration test style) | Upload test file daily, alert on failure |
| Set up Slack/Email alerting pipeline | Include errors + daily success heartbeat |
| Define & track SLOs for enrichment latency & success rate | e.g., 99% enrichment success within 60s |
| Set up end-to-end automated test pipeline | E2E coverage for all file types and flows |

🧩 EPIC: File Collection & Scenarios
|| Story || Comments ||
| [GS Fund] Collect files – Offshore (Mosaic Down) | PM report-backed |
| [GS Fund] Collect files – Onshore (Mosaic Down) | Same structure but different fund mapping |
| [Non-GS Fund] Collect files – Offshore (Casie Down) | Will involve TA variations |
| [Non-GS Fund] Collect files – Onshore (SS&C Down) | Includes client-initiated scenarios |
| Finalise format mapping + edge cases | For all above files |

🧩 EPIC: Fallback Connectivity – Feasibility
|| Story || Comments ||
| Analyse Calastone connectivity – fallback when Casie Down | For Non-GS offshore |
| Analyse BNY connectivity – fallback when SS&C Down | For Non-GS onshore |
| Propose automated upload route if feasible | SFTP/API based |
| Define what we support in Onshore PM reports but not Offshore | Document capability gap |

🧩 EPIC: Documentation
|| Story || Comments ||
| Document input/output format specs | Per fund type and region |
| Define onboarding guide for assistant team | Especially for contingency portal usage |
| Maintain lookup table structure versioning | For long-term maintainability |
| Confluence page linking all components | UI → API → Enrich → Dynamo → Output |

