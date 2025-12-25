## Change
Active Directory domain controller was created and verified as operational.
A Linux service server attempted Active Directory discovery using standard DNS-based mechanisms.

## Explanation
Domain discovery failed because the **AD-integrated DNS forward lookup zone was absent** on the domain controller.

Although the DNS role was installed and the domain existed, no forward lookup zone was present and no Active Directory service (SRV) records
(`_ldap._tcp`, `_kerberos._tcp`) were published.  
As a result, the domain was undiscoverable to non-Windows systems despite correct network connectivity.

At this stage, the domain name was **`lab.example`**.

## Expected Impact
Any Linux system attempting to discover, join, or authenticate against the domain would fail at the discovery stage until Active Directory
successfully created and published its DNS zones and service records.

## Root Cause
The initial Active Directory promotion occurred in an environment that was not fully prepared:
- DNS was not correctly initialized at promotion time
- Network configuration was inconsistent
- The resulting promotion completed without creating the AD-integrated DNS zone

This led to a valid directory service without an authoritative naming layer.

## Resolution (Historical)
The issue was resolved by **rebuilding the Windows Server** with:
- Static IP configuration applied before role installation
- Proper DNS configuration during promotion
- Clean Active Directory promotion as the first domain controller

During this rebuild, the domain was renamed to **`int.acme.com`** for clarity and convenience.

This resulted in the automatic creation of the AD-integrated DNS zone and service records.

## Boundaries
This issue was isolated to the **naming layer at promotion time**.
Network connectivity was functional.
No authentication, authorization, or user configuration was attempted during this stage.
