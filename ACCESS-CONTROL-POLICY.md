# Access Control Policy

**Policy Owner/Security Officer:** Garrett Jones
**Version:** 1.0  
**Last updated:** 2025-08-28

## Identity & Access Management
- **Identity provider**: Single-user Google account.
- **Roles**: Owner/User. No other roles or users.
   - There are no employees or contracts. If that changes, accounts follow least‑privilege RBAC with immediate de‑provisioning on role change or termination.
- **Authentication**: Passkey or hardware‑backed MFA is required.
- **Session security**: Auto‑lock maximum is 10 minutes. Device unlock requires biometrics or strong PIN/password.
- **Non‑human access**: All processes will execute when triggered by Owner/User. In the future, scheduled jobs may be created for automatic refreshes.
- **Periodic review:** Review user access to resources quarterly.
