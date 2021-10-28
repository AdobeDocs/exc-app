**[@adobe/exc-app](../README.md)**

> [Globals](../README.md) / [permissions](../modules/permissions.md) / PermissionsApi

# Interface: PermissionsApi

APIs to get permissions. An app in unified shell can consume PALM ACL service.

## Hierarchy

* **PermissionsApi**

## Index

### Methods

* [get](permissions.permissionsapi.md#get)

## Methods

### get

▸ **get**<T\>(`params`: [Parameters](permissions.parameters.md)): Promise<[PermissionsResponse](permissions.permissionsresponse.md)<T\>\>

Gets permissions based on the specified parameters.

#### Type parameters:

Name | Type |
------ | ------ |
`T` | [Permissions](permissions.permissions-1.md) |

#### Parameters:

Name | Type | Description |
------ | ------ | ------ |
`params` | [Parameters](permissions.parameters.md) | Parameters used to identify permissions to retrieve. |

**Returns:** Promise<[PermissionsResponse](permissions.permissionsresponse.md)<T\>\>

A promise for the specified permissions.
