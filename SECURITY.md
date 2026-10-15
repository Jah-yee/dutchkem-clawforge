# Security Policy

## Threat Model

Clawforge handles wallet signing, USDC settlement, and audit chaining. The following
threats are in scope:

- **Key compromise** — signing keys are stored encrypted at rest (AES-256-GCM) in
  `src/clawforge/crypto/vault.py`. Access requires the vault passphrase from the
  environment. Compromise of the passphrase or the host filesystem is out of scope.
- **Transport interception** — all external calls assume HTTPS termination at the
  trust boundary. Plaintext HTTP is not supported in production.
- **Unauthorized signing** — the signer enforces least-privilege semantics. Only
  approved transaction types are signed, and spend limits are enforced per account.
- **Replay / tampering** — audit chains are hash-linked. Any break in the chain
  invalidates downstream records.
- **Malicious inputs** — all external inputs are validated via Pydantic models and
  regex constraints before reaching business logic.

## Reporting a Vulnerability

If you believe you have found a security issue, please email security@dutchkem.example
with:

1. A description of the issue
2. Steps to reproduce
3. Potential impact
4. Any suggested mitigation

Please do **not** open a public GitHub issue for security reports.

We aim to acknowledge reports within 72 hours and provide a remediation timeline
within 7 days.

## Supported Versions

Only the latest release on `main` is supported with security updates.

## Disclosure

We follow coordinated disclosure. Once a fix is released, we will publish an
advisory describing the issue and credit the reporter (unless anonymity is
requested).
