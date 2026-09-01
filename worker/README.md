# زمردة — Backend security layer

The static site cannot provide shared admin authentication or a shared product database by itself. For production admin management without redeploys, deploy a Cloudflare Worker + D1/KV (or another authenticated backend) and connect the admin UI to it.

Required controls: WebAuthn/passkeys or strong password auth, secure HttpOnly SameSite cookies, CSRF protection where applicable, server-side validation, admin authorization on every mutation, rate limiting, audit logging, upload validation, secret storage in Worker secrets, and least-privilege database access.

Do not put admin passwords, API tokens, database credentials, or WhatsApp secrets in the frontend.
