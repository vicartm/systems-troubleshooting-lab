# Service Server — Baseline

## Intent
This system is intended to act as a service provider that relies on centralized identity for access decisions and does not authenticate users independently.

## Baseline state
- Linux server operating system installed and boots successfully.
- Local console access is available.
- Only local authentication is configured.
- No centralized identity or external trust configured.
- No application or user-facing services exposed to clients.

## Observations
- Login attempts with non-existent users fail immediately.
- Local root login succeeds on the console.
- System presents a text-based login environment with no graphical interface.

## Boundaries
- This state cannot be responsible for centralized identity failures.
- This state cannot explain client access failures to services.
- This state cannot cause authorization or trust relationship issues between systems.
