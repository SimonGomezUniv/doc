## Auth Microservice

Goal of this TD is to implement a simple oAuth2/OpenID microservice


## Dedicated OpenID instance create a new folder and new node server

expose a form to register a login / password
store them in a file (we should use a DB once again)
- store the password in plain text
- register with admin/admin
- re think your password storage and use AES256

expose a simple form waiting for a user / password

ensure that you can log in

implement the oAuth2/OpenID direct flow mecanism with redirect URI and token response

ensure you can connect to motus
ensure you can use the token to call the API score 

ensure you get an error trying to set the score of another user


## Keycloack instance 

use docker image quay.io/keycloak/keycloak:19.0.2 to spawn a keycloak instance 

configure a new client, the client is going to be your motus app.

Follow the tutorial to set up your OpenID client https://auth0.com/docs/quickstart/webapp/express



## Automatisation

integrate this new server in a DockerFile

 create a DockerCompose that run both server

## Bonus 

- implement a login with goole
- implement an authorization code flow

