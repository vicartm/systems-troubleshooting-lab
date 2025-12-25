## Change
Restored correct DNS authority for the Active Directory domain `int.acme.com`.

## Issue
Active Directory existed and the domain was created, but clients could not discover AD services.
SRV lookups for `_ldap._tcp.int.acme.com` returned `SERVFAIL`.

## Root Cause
The Domain Controller was not using itself as the primary DNS server.
AD service discovery queries were forwarded to non-authoritative DNS servers.

## Resolution
- Configured the Domain Controller to use its own IP as primary DNS.
- Configured public DNS servers only as DNS forwarders.
- Updated Linux client to use the Domain Controller as DNS.
- Verified successful SRV record resolution.

## Result
DNS-based Active Directory discovery is functional.
Linux clients can locate AD services and proceed with domain join.
