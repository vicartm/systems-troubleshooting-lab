# Identity Server — Baseline

## Intent
This system is intended to act as the centralized identity authority for the environment, serving as the single source of truth for user identity and authentication decisions for other systems.

## Baseline state
- Windows Server operating system installed and boots successfully.
- Local administrator access is available.
- Server Manager launches by default on login.
- No identity roles or directory services configured.
- No centralized identity, domain, or external trust relationships present.

## Observations
- System presents a graphical management interface by default.
- Server Manager prompts for further configuration and role installation.
- Local login succeeds using built-in administrator credentials.
- The system operates as a standalone server.

## Boundaries
- This state cannot be responsible for identity assertion or authentication failures between systems.
- This state cannot explain service access or authorization failures.
- This state cannot cause trust or dependency issues, as no identity services are active.
