# Security Overview for Alkaline.Org Transaction Downloader

**Tool Owner/Developer**: Garrett Jones
**Last updated**: 2025-08-28

## Definitions
- **Owner**: The owner of the Google Colab workflow.
- **User**: The owner of the source financial account and the target Google Sheet. Same person as the Owner but in a different role.

## Scope
* See [[README.md]] for a description of the tool.
* **Data sources**: Plaid (Transactions + Accounts/Balance).
* **Target financial institutions**: Initially, Chase credit card accounts (via OAuth). Others to be added later.
* **Data sharing**: There is no third-party data sharing.
* **User**: The Owner/User running the workflow in Google Colab must have access to both the financial institution with the transactions and the Google account where the transactions will be saved.
   - The location of User's Output Google Sheet is saved in Owner's Google Colab.

## High‑level data flow (run by User)
1. Create a short‑lived `link_token`, then launch **Plaid Hosted Link** to connect the account.
2. Exchange the returned `public_token` for an `access_token` in the Colab backend.
3. Fetch transactions via `/transactions/get`.
4. Write raw transactions to a User-configured Google Sheet in the User's Google Drive.
   - Sheets/Drive are encrypted at rest by Google.
   - Transactions are not retained in the Colab after the workflow terminates.
   - The transaction data is now outside the scope of the tool and fully in the user's explicit control.

## Risk minimization
- **Data request scope**: Only Transactions (and Accounts/Balance) products are requested in `link_token` to minimize scope.
- **Logging**: No sensitive data is logged (no tokens, no full payloads).
- **Vulnerability management**: See [[VULNERABILITY-MANAGEMENT-POLICY.md]] for details.
- **Encryption**: Keys are **derived per session** from a User-provided passphrase and are not stored.
- **Secrets**: `PLAID_CLIENT_ID` and `PLAID_SECRET` are stored in the Secrets configuration of Colab and are not present in the Colab code.
   - No tokens or secrets are commited to version control.
- **Access**: Only the Owner/User has access to the Google Colab.
- **Transport security**: All Plaid API calls, OAuth redirects, and Google API calls use **TLS 1.2+**.
