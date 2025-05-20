Hi Team,

Hope you're doing well.

Regarding the TechRisk ticket concerning the session ID validation in the API, I wanted to clarify a few points:

While the reported issue theoretically appears to be a potential vulnerability due to limited validation, in practice it is not the case. The system is designed in such a way that even the same user cannot reuse an old session ID. The session logic enforces that each session ID is single-use and tightly scoped to a specific action or login state.

That said, during my review of the current validation logic, I believe we can enhance the robustness of the API by adding an additional check — specifically:

Session ID Validation: Ensure the session ID is indeed associated with the currently logged-in user.

Vendor Association Check (Optional): If we want to add early-stage validation, we can also verify whether the vendor associated with the session ID matches the vendor assigned to the user.

These additions would further strengthen our defense-in-depth posture without altering the intended behavior of the API.

Let me know your thoughts or if you'd like me to proceed with these enhancements.

Best,
Angad

