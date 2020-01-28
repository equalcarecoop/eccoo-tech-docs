# identity and access subsystem

The Identity and Access subsystem is responsible for the security of the overall platform. This will ensure that the users are uniquely and securely [identified](identity-component.md) when [logged on](authentication.md), enabling [authorised](authorisation.md) \(and preventing unauthorised\) access to features, functions and data. It will also [track access](audit-component.md) to sensitive information for audit purposes. This will also encompass the [registration](registration.md) of users, including all platform provisioining \(register with graph, create security tokens and certificates if required\).

There is some question about whether the [roles](../relationships-subsystem/roles-component.md) component is part of the identity and access subsystem. At present, it is placed in the relationships subsystem. This may change as the implementation becomes clearer.

