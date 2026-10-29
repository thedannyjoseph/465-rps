# Rock Paper Scissors study
Open index.html in a modern browser. Participants enter details and the treatment assigned in person: A = 8, B = 16, C = 32 rounds.

After play, Predict my own score opens the Google Form and reveals Step 2. Participants submit the form, obtain the passkey from the researcher, and download their own session CSV. There is no participant-page researcher dashboard or all-participant download.

The passkey is configured in CONFIG.researcherPassphrase (currently fanouicae). Researchers must verify form submission before providing it: the standalone page cannot verify Google Forms submissions. A client-side passkey is only a workflow gate; it can be found in source and local browser records remain accessible. Server-side access control is required for secure enforcement.

Downloads are plain CSV, not encrypted. Previous private key/tool files are kept separately in case older encrypted downloads need recovery; do not distribute them.

Records remain in this browser localStorage. CSV exports contain only the current participant. Google Form responses are separate. Session totals repeat per round row: aggregate by session_id to avoid double-counting.
