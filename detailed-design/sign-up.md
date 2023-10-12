# sign-up

![Sign-up screen flow](<../.gitbook/assets/Eccoo Sign-up.png>)

Notes:

* All ui screens are in the sign-up module
* Need some kind of authenticated session in the UI to store registration details
* Keycloak must pass the session token back as part of the login session

## Design

### Login state

* Need the ability to logout
* Need the ability to login and redirect to a prior location

### Storage of sign-up session

* The sign-up session prior to the keycloak screens needs to take place in an unauthenticated state.
* Prior to redirecting, the sign-up session data (hat and postcode) is stored in the redis store under an signup identifier.
* The redirect uri that keycloak will redirect to encodes this session ID as part of the path.
* This will enables the UI server to recall this sign-in detail once the session is redirected.

