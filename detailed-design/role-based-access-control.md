# role-based access control

### Setting up RBAC in keycloak

#### Create a client

Create a new client role in the Web client (e.g. platform-admin)

![](<../.gitbook/assets/image (11).png>)

#### Map the client

1. Navigate to Clients -> web -> Mappers.
2. Select **Add builtin** and then search for Client roles and add this
3. Edit the client role to rename the claim to `roles` and also select add to userinfo and add to ID token.

![](<../.gitbook/assets/image (15).png>)

#### Setup a group

1. Navigate to Groups and create a Platform Group.
2. Under this, create an Administrators Group
3. Edit the Platform/Administrators group, navigate to Role Mappings and add the platform-admin client group

![](<../.gitbook/assets/image (6).png>)

#### Add users to the group

Users can now be added to the group, and should be associated with the specified roles.

