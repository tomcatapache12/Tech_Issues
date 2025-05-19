Hi All,

Following up on our ongoing discussion regarding the Log4j upgrade, I had a detailed conversation with Raghuvir today to align on the immediate next steps.

As discussed:

I have initiated a detailed review of the MR, which currently involves 162 file changes. I've already provided some initial comments, many of which Raghuvir has addressed. The review is still in progress, and I will continue to go through it thoroughly over the coming days.

Nagesh Gurudutt is supporting Raghuvir on the Keystone execution side.

From my side, I’m focusing on the MR review and have also shared guidance with Raghuvir on how to identify which scripts were modified and where they are being used within the project. Specifically, he can search for the modified scripts within the GTEM project and trace which Autosys jobs they are associated with to ensure proper testing coverage.

For the Java class-related changes, the GTEM team can assist in validating if these classes are bound to any business flows and help test their execution where applicable.

For the script-level changes, as mentioned earlier, Raghuvir can locate the relevant Autosys jobs through search. Harmeet is also supporting on the Java side and helping identify the correct Keystone instances involved with the script executions.

Going forward, Raghuvir will proceed with the verification and testing across both key areas:

Java class changes — with help from GTEM where needed.

Script changes — by tracing associated Autosys jobs and testing accordingly.

Thanks everyone for your continued support. Please feel free to reach out if any further assistance is required.

Best regards,
Anga
