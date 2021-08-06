**[@adobe/exc-app](../README.md)**

> [Globals](../README.md) / [session](../modules/session.md) / SessionScope

# Enumeration: SessionScope

Sets the scope validity. Ensuring a session can not be used outside of its context.

## Index

### Enumeration members

* [CONTEXT](session.sessionscope.md#context)
* [ORG](session.sessionscope.md#org)
* [USER](session.sessionscope.md#user)

## Enumeration members

### CONTEXT

•  **CONTEXT**:  = "context"

Context - Session is valid for the current user, organization and context only.
Context depends on the solution - Could be Sandboxes or Sub orgs.

___

### ORG

•  **ORG**:  = "org"

Organization - Session is valid for the current user and organization only.

___

### USER

•  **USER**:  = "user"

User - Session is valid for the current user only.
