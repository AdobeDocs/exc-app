**[@adobe/exc-app](../README.md)**

> [Globals](../README.md) / appapi

# Module: appapi

The App API provides auxiliary APIs to fetch certain data types.

***Import:***

```typescript
import appApi from '@adobe/exc-app/appapi';
```

***Default export:***

[AppApi](../interfaces/app.appapi.md#interface-appapi)

***Usage:***
These APIs return promises, not properties, and will need to be
asynchronously loaded by calling `get`.

```typescript
const [analytics, ddam, target] = await Promise.all([
  appApi.get('analytics'),
  appApi.get('ddam'),
  appApi.get('target')
]);

```

API for fetching app data.

## Index

### Enumerations

* [AppIds](../enums/appapi.appids.md)

### Interfaces

* [AppApi](../interfaces/appapi.appapi-1.md)
* [AppResponse](../interfaces/appapi.appresponse.md)
