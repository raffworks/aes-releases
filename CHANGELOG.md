# AES Desktop Changelog

## v13.0 — Desktop Reliability (1 November 2026)

- Protects saved SMTP credentials using Windows DPAPI with migration from older AES configurations.
- Adds a local SQLite batch journal and Resume Pending Batch. Previously accepted rows are not automatically resent; uncertain submissions require review.
- Introduces connection and SMTP login Diagnostics with immediate progress feedback and privacy-safe reports.
- Separates License and About information, improves transient SMTP retries and updater rollback safeguards.
- Windows EXE metadata now lists RaffWorks Digital Services.
- Keeps scheduled sending behavior unchanged (no persistent scheduling).
- Windows x64 portable EXE, unsigned. SHA-256: `ce0598dc06da0e921f89b5d0defbe1a634c92c69691bc39399e94da7acdd6f50`.
- Windows build checks passed; automated tests do not replace real Windows SMTP and batch-resume testing.


## v12.8 — Stabilization Update (31 October 2026)

### Reliability
- Improved support for SMTP over SSL on port 465 and STARTTLS on port 587, including appropriate connection handling and timeout.
- Added an explicit **Needs review** result for uncertain SMTP submissions or partially refused recipients. These attempts are not automatically retried, to help prevent duplicate emails.
- Updated summary reporting to include the **Needs review** status.

### Updates and security
- Improved version comparison so the desktop offers an update only when a newer numeric version is available.
- Auto-update now requires a valid SHA-256 checksum from the license server before replacing the installed EXE. When verification metadata is unavailable, the application opens the download page instead.
- Published the Windows x64 desktop application as `AutomatedEmailSender.exe`.

### Compatibility
- Kept the existing **Exact**, **Contains**, and **Starts With** matching workflows.
- Preserved license and settings storage under `%APPDATA%\AES` as in v12.7.
- This release does not introduce Billplz or Stripe checkout in the desktop application.

### Release file integrity
- Windows EXE SHA-256: `7e77aea0106f4a721b2b01c7558297beef83b226a8c3658ea8877e90a6700839`
- File size: 48,641,770 bytes.
- Source for this desktop build: `raffworks/AES`, stabilization review branch `fix/admin-manual-portal-20261030`, tested Windows build SHA `106dd14d26f061573e7a8911ff51f65d307f3f1b`.

**Note:** Changes to the Admin Page, Customer Portal and server in AES PR #1 are separate from the desktop EXE release and are not deployed merely by publishing v12.8.

## v12.7 — Previous release (2 October 2026)
- Added Setup & User Guide links in Settings and About.
- Updated schedule sending to choose date, hour, and minute from dropdowns; a new schedule replaces a previous one.
