# Privacy Policy for Alkaline.Org Transaction Downloader

- **Policy Owner/Security Officer:** Garrett Jones
- **Effective date:** 2025-08-28

See [README.md](README.md) for a description of the tool.

This tool is used solely by a single individual (“Owner”). There are **no end‑users or customers**.

## Definitions
- **Owner**: The owner of the Google Colab workflow.
- **User**: The owner of the source financial account and the target Google Sheet. Same person as the Owner but in a different role.
- **User data**: Financial account metadata and transactions.

## What data is collected
- User data is retrieved from the User's linked accounts via Plaid.
- No marketing, analytics, or tracking are saved.

## How data is used and where it is stored
- The User data is transferred directly to a Google sheet of the User's choosing and then immediately discarded by the workflow.

## Data retention
- Only basic run logs with no user-identified data or sensitive data are retained. These logs may be kept indefinitely.

## Security
- TLS 1.2+ is used in transit. AES‑256‑GCM is used to encrypt any data stored at rest (but no data is stored at rest outside of the User's Google account). Access is protected by phishing‑resistant MFA.

## Your choices
- The User may disconnect accounts at any time in the Plaid Portal or the Plaid Dashboard. The User can delete their User Data from their Google Sheet at any time.
