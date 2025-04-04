Subject: Proposal: MVP Scope for Mosaic Contingency Platform

Hi [Team/All],

As part of our initiative to build a Contingency Platform for Mosaic, this email outlines the proposal for the MVP along with the initial scope we aim to cover in the first phase.

🎯 MVP Objective
To ensure continuity of trade flows and settlement in case of system disruptions by providing contingency paths across key areas — not assuming failure, but enabling fallback when needed.

📌 Initial Scope – MVP Phase
1. Contingency Strategy: Direct Connectivity to TA
Set up fallback paths to enable trade submission directly to the Transfer Agent (TA) or via Calastone. Applicable scenarios:

GS Onshore

GS Offshore

Non-GS Onshore (Calastone connectivity if required)

Non-GS Offshore (Calastone connectivity if required)

This includes supporting manual intervention without relying on Mosaic UI or downstream automation.

2. Trade Retrieval in Case of Queue/API Outage
In the event of any failure in queues, APIs, or upstream systems, the platform should allow:

Fetching impacted trades

Filtering based on source attributes such as trade channel, client, etc.

Ensuring completeness of trade data for fallback operations

3. Acknowledgment & Settlement Considerations
Incorporate acknowledgment and settlement dependencies to ensure end-to-end trade completion in contingency mode:

Cash Sweep

BofA acknowledgments

Citi acknowledgments

These acknowledgments must be available in the fallback flow to prevent settlement issues.

📝 Supporting Context
As per our discussion with the SS Team, we understand that in current failure scenarios, trades are placed directly with the TA via phone calls.

For onshore and offshore, the SS team reaches out to the TA manually upon failure.

In the offshore flow, we already have the capability to upload a file directly to the TA, which can be extended or streamlined in our MVP.

Let me know if there’s anything to add or refine. This scope will also be documented on Confluence under the “Contingency Platform” section.

Best regards,
[Your Name]
