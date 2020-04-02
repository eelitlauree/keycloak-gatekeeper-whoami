# Manual Keycloak Configuration

## Create client - whoami

1. Create client whoami

    |Field| Value|
    | -- | -- |
    | Client ID | whoami |
    | Client Protocol | openid-connect |
    | Root URL | http://whoami.localhost |

    ![Create Client](./img/create-client.png "create client")

2. Edit client whoami

    |Field | Value|
    | -- | -- |
    | Access Type| confidential |

    ![Crendential Client](./img/credential-client.png "credential client")

2. save

3. Go to credentials

4. Copy **Secret**, you need this value on gatekeeper config

    ![Copy Client Secret](./img/copy-client-secret.png "copy client secret")

## Create client scope - whoami

1. Create Client Scope whoami

    | Field | Value|
    | -- | -- |
    | Name | whoami |
    | Description | whoami |
    | Protocol | openid-connect |
    | Display On Consent screen | ON |
    | Consent Screen Text | |
    | Include In Token Scope | |
    | GUI order | |

    ![Create Client Scope](./img/create-client-scope.png "create client scope")

2. save

3. create Audience mapper in the scope

    ![Create audience mapper 1](./img/create-audience-mapper-1.png "create audience mapper 1")

    | Field | Value |
    | -- | -- |
    | Protocol | openid-connect |
    | Name | whoami |
    | Mapper Type | Audience |
    | Included Client Audience | whoami |
    | Included Custom Audience | |
    | Add to ID Token | ON |
    | Add to access token | ON |

    ![Create audience mapper 2](./img/create-audience-mapper-2.png "create audience mapper 2")

4. save

## Associate client and client scope

1. Go to client whoami
2. Go to Client Scopes
3. Select "whoami" from "Available Client Scopes"
4. Click "Add selected" button

    ![Result associate client scope](./img/associate-client-scope.png "associent client scope")
