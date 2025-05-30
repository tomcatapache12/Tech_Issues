h2. Functional Requirements

|| ID || Requirement || Description || Priority ||
| FR-1 | File Upload | Allow authorized users to upload trade files (CSV/Excel). | High |
| FR-2 | Trade File Validation | Validate file format, mandatory fields, and data correctness after upload. | High |
| FR-3 | Data Display | Show the contents of the file for user confirmation post-upload. | Medium |
| FR-4 | Data Transformation | Convert uploaded file into TA-readable format using DB lookup and predefined mapping logic. | High |
| FR-5 | Download Output File | Allow download of the transformed file in the required format. | High |
| FR-6 | Access Control | Restrict access to internal users with role-based permissions (Viewer, Operator, Admin). | High |
| FR-7 | Manual Override | Allow operators to edit trade details before transformation in special cases. | Medium |
| FR-8 | Dashboard Monitoring | Display status of uploads, processed files, and transformation history. | Low |
| FR-9 | Audit Logging | Log all actions (uploads, downloads, transformations) with timestamps and user info. | High |
| FR-10 | Contingency Mode Toggle | Enable/disable contingency mode manually by Admin based on Mosaic UI availability. | Medium |
| FR-11 | Support for Multiple Scenarios | Initially support Mosaic UI down + Casie up, and Casie down + Calastone up; extendable to future cases. | High |



h2. Non-Functional Requirements

|| ID || Requirement || Description || Priority ||
| NFR-1 | Availability | Platform should be available 99.5% of business hours. | High |
| NFR-2 | Performance | File processing and transformation should complete within 3 seconds for up to 500 rows. | High |
| NFR-3 | Security | Encrypt data at rest and in transit. Implement RBAC and possibly SSO integration. | High |
| NFR-4 | Usability | Simple UI with tooltips, validations, and user guidance. | High |
| NFR-5 | Audit & Compliance | Store logs for 90 days and allow export. | Medium |
| NFR-6 | Maintainability | Modular code structure and standard logging practices. | Medium |
| NFR-7 | Disaster Recovery | Data backup should allow recovery within 4 hours during outages. | High |
| NFR-8 | Logging & Monitoring | Integrate with monitoring tools (e.g., Splunk, Prometheus) and set up alerts for critical errors. | Medium |
| NFR-9 | Scalability | Handle concurrent uploads without slowing down. | Medium |
| NFR-10 | Extensibility | Easy addition of new trade types, file formats, and transformation logic. | Medium |
