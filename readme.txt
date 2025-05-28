Here's a professionally worded, polite email you can send to communicate the situation without assigning blame:


---

Subject: Deployment Issue Identified in Non-Prod – Seeking Approval for Next Steps

Hi Bhagavathi and Trupti,

Hope you're doing well.

We’ve identified an issue during the non-prod deployment that was not caught during dev testing or regression. After evaluating the impact and possible options, we’d like to propose the following two paths forward and seek your guidance:

1. Proceed with deployment of all services except the outbound service, which can be kept on the previous version as there are no changes in this release for it.

This would introduce a slight inconsistency in deployed versions across services.

We would need your approval to move ahead with this approach.



2. Revert the recent changes and plan for a fresh round of regression testing, followed by a clean deployment.

This will ensure consistency but will require additional time for testing and validation.




Please let us know your preferred option, and we’ll proceed accordingly.

Best regards,
Angad


---

Let me know if you'd like to include any specific issue description or Jira ID for tracking.
