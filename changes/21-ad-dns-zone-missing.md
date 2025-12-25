# AD-Integrated DNS Zone Missing

## Change
Active Directory domain controller was created and verified as operational. Linux service server attempted Active Directory discovery using standard mechanisms.

## Explanation
Domain discovery failed because the AD-integrated DNS zone for the domain (lab.example) was not present on the domain controller. While the DNS role was installed and the domain existed, no forward lookup zone or AD service (SRV) records (_ldap._tcp, _kerberos._tcp) were available. This made the domain undiscoverable to non-Windows systems despite correct network connectivity and split DNS configuration.

## Expected impact
Any Linux system attempting to discover, join, or authenticate against the domain will fail at the discovery stage until Active Directory publishes its DNS zones and service records.

## Boundaries
This issue is isolated to the naming layer. Network connectivity, routing, split DNS configuration on Linux, and Active Directory identity services are confirmed to be functional. No authentication, authorization, or user configuration has been attempted.
