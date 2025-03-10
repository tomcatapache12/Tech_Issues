Title: Resolving Splunk Peer "Down" State Issue

📝 Background
In a Splunk distributed environment, you may notice that some peers are marked as "Down" in the cluster master. This typically happens because the peer was not activated when the master started, causing the peer to miss the initial registration process.

To resolve this, you need to manually authenticate and register the affected peers.

Additionally, a ticket has been created to analyze the feasibility of automatically registering peers once they become available.

🔎 Steps to Resolve the Issue
Follow the steps below to manually fix the issue:

1. Login to Splunk
Open the Splunk portal.
Log in using an account with admin privileges.
(Example Screenshot)

2. Go to Settings
From the top-right corner, click on Settings.
(Example Screenshot)

3. Navigate to Distributed Environment
Under the Settings menu, go to the Distributed Environment section.
(Example Screenshot)

4. Open Distributed Search
Select Distributed Search from the Distributed Environment section.
(Example Screenshot)

5. Select Search Peers
Click on Search Peers.
You will see a list of configured peers and their statuses.
(Example Screenshot)

6. Click on the Peer URI
Identify the peers marked as "Down."
Click on the Peer URI for each down state peer.
(Example Screenshot)

7. Authenticate Each Remote Search Peer
After clicking on the Peer URI, authenticate the peer manually.
This will establish a connection and mark the peer as "Up."
(Example Screenshot)

✅ Expected Outcome
Once authentication is successful, the peer should switch to a "Healthy" state.
The cluster master should now reflect the correct status for the peer.


Subject: Steps to Resolve Splunk Peer "Down" State Issue

Hi Team,

If you encounter Splunk peers showing as "Down" in the dashboard, it is happening because the peer was not activated when the master started. As a result, the peer was not registered at that time and was marked as "Down." To resolve this, you need to manually authenticate and register the peer.

Please follow the steps outlined in the Confluence page below to fix the issue:

👉 Steps to Resolve Splunk Peer "Down" State

Summary:

The issue occurs because the peer was not available when the master started, causing it to miss the registration process.
A ticket has been created to analyze the feasibility of automatically registering peers as "Up" once they become available or introducing a delay to allow peers to register before marking them as down.
Please feel free to reach out if you have any questions or need further assistance.

Best regards,
Angad






Next Steps
A ticket has been created to investigate the feasibility of automatically registering peers when they become available.
Further updates will be shared once the analysis is complete.

