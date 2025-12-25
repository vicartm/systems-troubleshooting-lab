# Identity Role Introduced

## Change
- The Active Directory Domain Services (AD DS) role was installed on the identity server.
- No domain has been created.
- No clients or services have been joined or configured to use this server.

## Explanation
Active Directory Domain Services is a system that allows one computer to act as a central authority for user identities.  
Instead of each computer managing users independently, AD DS provides a shared directory where users and computers can be defined once and then recognized by other systems.  
Its purpose is to consistently answer the question “Who is this user?” across multiple machines.

## Expected impact
- The server is now capable of acting as a centralized identity authority.
- Identity-related configuration can be performed in later steps.
- Other systems could eventually rely on this server for authentication once a domain is created.

## Boundaries
- No centralized identity is active until a domain is created.
- No other system depends on this server yet.
- Any access or authentication failures on other machines cannot be caused by this change alone.
