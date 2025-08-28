# Information Security Policy for Alkaline.Org Transaction Downloader

**Policy Owner/Security Officer:** Garrett Jones
**Version:** 1.0  
**Last updated:** 2025-08-28

## Policy Purpose
Protect the confidentiality and integrity of financial data accessed via Plaid by the Alkaline.Org Transaction Downloader. See [[README.md]] for a description of the tool.

## Roles & responsibilities
- **Policy Owner/Security Officer:** Implements and enforces this policy.
- **Owner**: The owner of the Google Colab workflow.
- **User**: The owner of the source financial account and the target Google Sheet. Same person as the Owner but in a different role.

## Key principles
- **Least privilege:** Only the Owner has access to the workflow.
- **Data minimization:** Collect only what's required for downloading and transfering transaction data.
- **Encryption:** Use TLS 1.2+ in transit and apply AES‑256‑GCM for any data stored at rest that is not stored in Google Drive/Sheets.
- **Secret handling:** Don't store any secrets in source control. Rotate secrets at least once a year, and additionally when compromise is suspectred.
- **Device security:** Auto-update OS and browsers that are used to execute the workflow.
- **MFA:** Use phishing‑resistant MFA (passkey/hardware key) for the Google Account that the workflow is stored in.
- **Logging:** Don't store sensitive data in logs.
- **Third parties:** Don't share any data with third parties. Only access and store data in Owner/User accounts.
- **Review cadence:** Review this policy yearly.

## Incident response
1. Contain incident: Revoke Plaid secrets.
2. Eradicate vulnerabilities: Patch devices, update Google account password, update Colab dependencies, restrict Google Sheet access, identify workflow security loopholes.
3. Recover from incident: Issue new Plaid secrets, verify workflow is working.
4. Future prevention: update this policy based on learnings from the incident.
