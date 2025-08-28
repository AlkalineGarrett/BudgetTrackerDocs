# Data Retention & Disposal Policy

**Policy Owner/Security Officer:** Garrett Jones
**Version:** 1.0  
**Last updated:** 2025-08-28

See [[README.md]] for a description of the tool.

## Definitions
- **Owner**: The owner of the Google Colab workflow.
- **User**: The owner of the source financial account and the target Google Sheet. Same person as the Owner but in a different role.

## Data classes
- **Tokens & IDs**: Plaid `access_token`, `item_id`, and account IDs.
- **Raw transaction data**: Transaction payloads returned by Plaid.
- **Output Google Sheet**: The destination Google Sheet for transaction data.

## Retention
- **Tokens & IDs:** Tokens are retained only while workflow is active.
- **Raw Transaction data**: No transaction data is retained by the workflow, which operates ephemerally.
- **Output Google Sheet**: The location of the Google Sheet is saved in Owner's Google Colab. The Google Sheet itself is under User control and is outside the scope of this policy. The User can decide to keep data in this Google Sheet indefinitely.

## Storage & encryption
- Any saved data is encrypted at rest (AES‑256‑GCM). Keys are **not** stored; they are derived from a passphrase per session and must be re‑entered.

## Disposal
- Revoke Plaid Items in the Dashboard when no longer needed.
