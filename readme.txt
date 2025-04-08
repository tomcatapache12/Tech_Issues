
Minutes of Meeting:

Onsure-like Tool for Offshore:
Thomas raised the need for a tool similar to the one in Onsure for TA contingency. This would help avoid manual calculations of net value or net flow for trades before sending them to the Portfolio Manager. The goal is to automate this process for Offshore as it currently stands for Onsure. Rini will help clarify how the tool works in Onsure, and we will discuss replicating this for Offshore.

Post-Reconciliation Capability for GS & Non-GS Funds:
Thomas suggested adding post-reconciliation capabilities as part of the MVP. This will cover both GS and non-GS funds, which are currently handled manually after TA failures. The idea is to automate the reconciliation process so that our system can sync with the latest data when TA is down, eliminating manual efforts.

Offshore Client Formats:
Thomas emphasized the need to collect all formats used by Offshore clients. Specifically, we need to gather the formats sent by clients for GS and non-GS funds, especially in failure scenarios. This will help ensure that our system can accommodate these different formats in case of failures.

TA Down – Priority Cases and Solutions:

TA Downtime: The primary use case for this project is handling scenarios when TA is down. We will prioritize solving this case first.

FTP for File Upload: Thomas suggested utilizing FTP capabilities at the TA site to replace the current manual file upload strategy, which is used for dividend processing. We will explore this solution further.

Calistone-like Data Format: When TA is down, email alerts containing data should follow a similar format to Calistone, making it easier for our system to utilize and upload the data into Calistone automatically.

Income Contingency Screen:
Thomas mentioned an income contingency screen, but the specifics are unclear. Angad will confirm the details with Thomas.

Class Takeaway:

The team needs to focus on automation for manual processes, especially regarding post-reconciliation and data uploads during TA downtime.

There is a need to understand existing tools (like the one in Onsure) and replicate them for Offshore, with a focus on reducing manual work.

Attendees:

Angad

Thomas

Rini (for Onsure tool details)

Playback Blocker or Priorities:

Priority 1: Automate handling of TA downtime scenarios and post-reconciliation.

Priority 2: Gather Offshore client formats for GS and non-GS funds.

Priority 3: Investigate FTP capabilities for file upload at TA site.

Priority 4: Confirm details with Thomas regarding the income contingency screen.
