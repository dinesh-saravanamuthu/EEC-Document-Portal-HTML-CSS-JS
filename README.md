# EEC Digital Academic Document Portal — Vanilla HTML/CSS/JavaScript

This is a standalone, framework-free frontend conversion of the CollegeDocumentPortal project. It uses only:
- `index.html`
- `styles.css` (retains the original portal stylesheet)
- `app.js` (vanilla JavaScript; no React, router, Axios, icon package, or build step)
- `eec-mark.svg` (college mark)

## Run locally
1. Extract the ZIP.
2. Open `index.html` in a modern browser, or serve the folder with VS Code Live Server.
3. Select **Student** or **Staff / Admin** on the login page.

### Student workflow
- Sign in with any email for the local preview.
- Sample student records are available by signing in as `aarav.kumar@example.edu` or `diya.raj@example.edu`.
- Register a local student profile.
- Submit document requests, search and view requests, read messages, and print/save issued document text.
- Documents marked **Document Ready** appear in the vault.

### Staff / Admin workflow
- Select **Staff / Admin**, enter any non-empty name and passphrase to open the local preview workspace.
- Search and filter requests, view request details, send messages, update status, supply final document text, and export the requests as CSV.
- A request cannot be marked **Document Ready** unless final document text has been supplied.

### Example data
Two fictional sample requests are seeded on first run:
- EEC-2026-1001 — Bonafide Certificate — Document Ready
- EEC-2026-1002 — Official Transcript — Under Verification

## Important scope and security limitations
The uploaded original is a full-stack app using React, a backend API, PostgreSQL, JWT authentication, and email OTP. A truly framework-free, standalone HTML/CSS/JS-only app cannot retain server-side authentication, email delivery, a shared database, server audit logs, or live multi-user synchronization without retaining or replacing a backend service. This converted edition is therefore an offline/local preview: its data is stored in this browser's `localStorage`, and its role selection/passphrase are **not secure authentication**. The local verification link only checks local browser records; it is not an official server-backed verification. The print action opens a print-ready page, allowing the browser to save it as PDF. It does not generate the original cryptographically verifiable PDF/QR document.

Do not store real student personal information or use this offline version for official issuance. To preserve production-grade OTP, authorization, database, QR/SHA-256 verification, and shared records, the original backend must remain available behind this frontend.

## Data reset
To reset the local demo data, open browser developer tools → Application/Storage → Local Storage and remove `eec_vanilla_portal_v1` and `portal_theme`, then reload.

## Verification
See `TEST-REPORT.txt` for checks performed and limitations.
