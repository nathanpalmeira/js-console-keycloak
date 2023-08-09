# Basic JavaScript Example
========================
## Configs

Open the src/main/webapp/keycloak,json file and change the settings as you wish

```json
{
  "realm" : "your_realm",
  "auth-server-url" : "/auth",
  "ssl-required" : "external",
  "resource" : "your_clientId",
  "public-client" : true
}

```
_realm_ = insert realm which you will login<br>
_auth-server-url_ = insert router complement (if keycloak <= 18 include "/auth" else leave empty) <br>
_ssl-required_ = If your realm has SSL as required, enter true in this field, otherwise leave false<br>
_resource_ = Insert client which you will login<br>
_public-client_ = Insert true to client public and false to confidetial


## Build

```mvn clen package```

## Deploy in Keycloak Quarkus

### With Docker

In Dockerfile include this line

```
ADD --chown=keycloak:keycloak ./folde/to/your/file/js-console.war /opt/keycloak/providers/js-console.war
```
### Without Docker

Include file ./folde/to/your/file/js-console.war in folder /opt/keycloak/providers