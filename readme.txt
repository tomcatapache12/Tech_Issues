
 Identifier Used for Non-GS Funds in TFA Screening
Discussion:
Clarified the identifier used in TFA screening to mark transactions as complete and prevent retransmission to Calastone or Bonibroker for non-GS funds.

Resolution:
The TA Account and Fund Code are used to identify trades and create the notification template. These identifiers are leveraged to mark the trade as complete in TFA.

2. Offshore Client Formats in Case of CASIE Down
Discussion:
Explored the formats used when CASIE is down, apart from the existing PV format.

Response:
There are three formats currently in use:

Citi File (XML): Used when Citi Mosaic is down and FinControl options are not working.

Contingency UI: Can be used when Mosaic Trade Service is down.

Custom Template (SSTM): Data received via phone call, then entered into a standard internal template.

Follow-up:
BOFA format needs to be finalized; the responsible team will provide input.

3. Feature Requirement for PM Report Value Calculation (Offshore)
Discussion:
Evaluated the usage of PM Reports UI for value calculation specific to offshore trades.

Observations:

UI currently supports both onshore and offshore filters.

Onshore team does not use this feature actively.

Further clarification is awaited from Thomas regarding required enhancements for offshore needs.

4. Custom Template and Cassie Format Conversion
Discussion:
Raised question on why the custom template is not directly in Cassie format.

Response:
Cassie format involves complex data structures. Hence, the teams prefer working with a fixed-format template, which is then looked up and converted into Cassie-compatible data.

