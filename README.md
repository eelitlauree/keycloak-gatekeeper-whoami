# Generic Keycloak Protection

This demo the use of keycloak gatekeeper to protect a simple web app. 

To start the demo, use the following command
```
docker-compose up -d
```

Archiecture of this setup

![Achitecture diagram](./img/traefik-keycloak-gatekeeper-whoami.png "Architecture")

Components
1. traefik
2. keycloak
3. keycloak-gatekeeper
4. whoami (simple web app)

ps. you must use Chrome to open the link

## traefik

http://localhost:8080

## keycloak

http://auth.localhost

```
username: admin
password: test
```

We created a client, a client scope and associate the client and client scope to make this demo work.

## keycloak-gatekeeper

http://whoami.localhost

```
username: user@email.com
password: test
```

After user is authenticated, http request will be proxy to whoami interface.

[Scuring App - Keycloak Gatekeeper](https://www.keycloak.org/docs/latest/securing_apps/index.html#_keycloak_generic_adapter)

## whoami

print the requeter's information, including request headers.

User and session info will be available in the request header

```
X-Auth-Audience: whoami,account
X-Auth-Email: user@email.com
X-Auth-Expiresin: 2020-03-31 09:30:50 +0000 UTC
X-Auth-Groups: 
X-Auth-Roles: offline_access,uma_authorization,account:manage-account,account:manage-account-links,account:view-profile
X-Auth-Subject: ad6fa1b4-5c89-4c19-9778-fabb24e9c3b5
X-Auth-Token: [Access Token]
X-Auth-Userid: user@email.com
X-Auth-Username: user@email.com
```

![whoami response](./img/whoami-response.png "whoami response")