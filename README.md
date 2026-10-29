# Rock Paper Scissors participant study

Open index.html in a modern browser. No installation or server required.

## Researcher setup
Edit CONFIG near the beginning of the script in index.html:
- researcherPassphrase: configured as `fanouicae`.
- recipientEmail: researcher email for the manual email draft (currently blank).
- randomTreatment: false lets participants enter the A/B/C treatment assigned by the researcher in person; true randomly assigns one.

A = 8 rounds, B = 16 rounds, C = 32 rounds. Participants enter their U-M email, first/last names, school year, and experience, play their assigned treatment, then click **Predict my own score** to open the Google Form in a new tab. The Google Form collects their score response separately; this HTML does not receive or confirm form submissions. The local CSV prediction fields remain empty. Scores and outcome labels are hidden during play. Choices are independently random using crypto.getRandomValues and rejection sampling.

## Results
Researcher downloads are gated by the configured passphrase. This client-side gate is not secure authentication; source and browser tools can reveal it and local records. For secure multi-device collection, use an authenticated backend.

Records stay in localStorage in this browser on this machine. CSV exports include participant details, treatment, prediction, outcomes, timestamps, and each round. Session totals repeat on each round row: group by session_id to avoid double counting. Incomplete sessions are retained. Refreshing starts a new session. Browser data removal can erase records; download backups. Use the same browser and file location for collection.

Sending is manual: when recipientEmail is configured, the send button downloads the CSV and opens an email draft. Attach the CSV and send it yourself. Automatic attachments and sending require a backend or collection service. No data is automatically transmitted.

Version 2 uses a separate storage key; earlier six-round game records remain untouched under ioe465-rps-v1.

All code is in index.html. No dependencies. Do not commit participant exports to GitHub.
