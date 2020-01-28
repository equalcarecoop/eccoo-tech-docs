# authentication

The authentication component is responsible for ensuring that the user accessing the platform can be clearly identified

## Critical Requirements

* Must support sign in for users using an open authentication method such as OAuth 2 / OpenID Connect
* Should support the ability to self-service reset passwords 
* Must support sign out from platform \(to avoid profiles being leaked on shared devices\)
* Should support use of extended authentication \(such as One Time Passwords\) for users with elevated privileges to reduce the risk of such accounts being compromised.

## Implementation details

Implementation of this component is closely linked to the selection of identity component.





