# Security boundary — زمردة

This frontend is a static site. Client-side controls are not a substitute for server-side security.

Implemented in this build:
- strict same-origin JavaScript policy via CSP meta tag
- no API keys or database credentials in frontend files
- external links use `noopener noreferrer`
- basic client-side order-field validation
- `object-src 'none'`, `frame-ancestors 'none'`, restrictive permissions policy
- security headers provided in `_headers` for compatible static hosts

Before production with real admin/data:
- add server-side authentication and authorization
- use secure, HttpOnly, SameSite cookies/sessions
- validate/sanitize all server inputs
- add rate limiting and abuse protection
- store products/orders in a protected backend/database
- configure HTTPS/HSTS at the host/CDN
- add audit logs and backups
- protect admin routes server-side; never rely on frontend hiding
