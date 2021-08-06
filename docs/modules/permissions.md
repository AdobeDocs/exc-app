**[@adobe/exc-app](../README.md)**

> [Globals](../README.md) / permissions

# Module: permissions

APIs to get permissions for a user. An app in unified shell can consume Permissions service.

To consume this API, add the following import to your code.

```typescript
import permissions from '@adobe/exc-app/permissions';
```

The default export is an object of type [PermissionsApi](../interfaces/_permissions_.permissionsapi.md)

API reference: [scroll down](#index)

### Sample code

```typescript
import permissions from '@adobe/exc-app/permissions';

const {permissions: perms} = await permissions.get({permissions: [
  'permission1',
  'permission2'
]});
```

All permissions can be requested using the key '*'
```typescript
import permissions from '@adobe/exc-app/permissions';

const {permissions: perms} = await permissions.get({permissions: ['*']});
```

## Index

### Interfaces

* [Parameters](../interfaces/permissions.parameters.md)
* [Permissions](../interfaces/permissions.permissions-1.md)
* [PermissionsApi](../interfaces/permissions.permissionsapi.md)
* [PermissionsResponse](../interfaces/permissions.permissionsresponse.md)
