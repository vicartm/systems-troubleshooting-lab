# Client — Baseline

## Intent
This system is intended to represent an end user, initiating access requests to services and relying entirely on upstream identity and service systems for authentication and authorization decisions.

## Baseline state
- Windows 10 operating system installed and boots successfully.
- Local user login is available.
- System is not joined to any domain.
- No centralized identity configured.
- No access to external services configured.

## Observations
- Graphical login screen is presented at startup.
- Local user login succeeds.
- No prompts or indicators related to domain membership or centralized identity are present.
- The system operates as a standalone client.

## Boundaries
- This state cannot be responsible for centralized identity failures.
- This state cannot decide or enforce authorization.
- This state cannot cause service-side access failures.
- Any future access issues must originate upstream in identity or service systems.
