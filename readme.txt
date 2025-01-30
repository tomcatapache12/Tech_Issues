Impact
GS Funds document links were not visible on the Mosaic UI post-release.
The issue was resolved by executing a pre-existing DACT query to insert missing records.
Root Cause Analysis (RCA)
Background:

A new table was created to store link mappings as part of the system enhancement.
All existing Non-GS Fund links were successfully migrated to the new table during the release.
For GS Funds, the plan was to refresh and migrate data by running an Autosys job post-release.
Since these GS Fund links had not been refreshed for several months, most of the data was assumed to be invalid.
Cause of the Issue:

On the release day, due to concerns about safety and multiple technical checkouts, I agreed to proceed with a partial release instead of a full release.
It was assumed that the data sync process would not delete existing GS Fund links, but this assumption proved to be incorrect.
During onshore hours, Ishaan identified the gap.
The issue was resolved by executing the pre-existing DACT query to insert all missing records.
Next Steps
Run the new Autosys job as soon as possible without any further delays.
Finalize and review the release plan at least one day prior to the release to avoid last-minute changes.
Ensure that all critical technical steps are validated during the tech checkout to avoid escalations, such as the one raised by the SS Team.
