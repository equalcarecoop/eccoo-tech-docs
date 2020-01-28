# authorisation

The authorisation component is responsible for the distribution of permissions to the users of the platform. The permissions will be granted based on roles fulfilled by the users, potentially in relation to other users.

## Critical Requirements

* Must provide permission grants for authenticated users
* Should to propagate claims between components to ensure security is maintained

## Implementation

Another component which can only be selected when the identity component is selected.

Should also propagate claims via techniques such as [JSON Web Tokens](https://jwt.io/). This ensures that there are no holes in the security implementation. UI and API components should pass and require such tokens.

