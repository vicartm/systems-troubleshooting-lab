# Initial Identity and Connectivity Progress

## Completed
- Windows Server installed and promoted to Domain Controller for lab.example
- Active Directory Domain Services operational
- DNS role installed on domain controller
- Fedora Linux service server installed
- Network connectivity verified between Fedora and Windows Server by IP
- Split DNS configured on Fedora (Windows DNS for lab.example, gateway DNS for external)
- DNS resolution path validated on Fedora

## Observations
- Active Directory identity services are active but undiscoverable to Linux systems
- DNS role exists but AD-integrated forward lookup zone is missing
- Discovery failures are deterministic and isolated to DNS service record publication

## Current State
Identity authority exists but is not externally discoverable. No clients or services depend on identity yet. System is in a controlled, partially configured state suitable for further diagnostics.
