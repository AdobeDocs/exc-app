**[@adobe/exc-app](../README.md)**

> [Globals](../README.md) / [network](../modules/network.md) / FetchScope

# Enumeration: FetchScope

This parameter will be used to specify what headers are automatically added to the API call.

## Index

### Enumeration members

* [AUTH](network.fetchscope.md#auth)
* [NONE](network.fetchscope.md#none)
* [ORG](network.fetchscope.md#org)
* [SANDBOX](network.fetchscope.md#sandbox)
* [SANDBOX\_PLUS](network.fetchscope.md#sandbox_plus)

## Enumeration members

### AUTH

•  **AUTH**:  = "AUTH"

*** auth: Authentication only. Only auth headers will be added: ***
authentication: Bearer <TOKEN>
x-api-key: exc_app or custom ID provided by SPA configuration

___

### NONE

•  **NONE**:  = "NONE"

***none: Minimal scope***
No headers are added. Use case: Non authenticated calls.

___

### ORG

•  **ORG**:  = "ORG"

*** org: Authentication + IMS Org. ***
authentication: Bearer <TOKEN>
x-api-key: exc_app or custom ID provided by SPA configuration
x-gw-ims-org-id: <IMS ORG ID>

___

### SANDBOX

•  **SANDBOX**:  = "SANDBOX"

*** sandbox: Authentication +IMS Org + PALM Sandboxes. ***
authentication: Bearer <TOKEN>
x-api-key: exc_app or custom ID provided by SPA configuration
x-gw-ims-org-id: <IMS ORG ID>
x-sandbox-name: <SANDBOX NAME>

___

### SANDBOX\_PLUS

•  **SANDBOX\_PLUS**:  = "SANDBOX\_PLUS"

*** sandbox-plus: additional headers required with sandbox . ***
authentication: Bearer <TOKEN>
x-api-key: exc_app or custom ID provided by SPA configuration
x-gw-ims-org-id: <IMS ORG ID>
x-sandbox-name: <SANDBOX NAME>
x-sandbox-type: <SANDBOX TYPE>
x-sandbox-default: <SANDBOX DEFAULT>
