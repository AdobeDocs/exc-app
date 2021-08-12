**[@adobe/exc-app](../README.md)**

> [Globals](../README.md) / capabilityapi

# Module: capabilityapi

API to request capability icons by id (or secondarily by display name).

***Import:***

```typescript
import capabilityApi from '@adobe/exc-app/capabilityapi';
```

***Default export:***

[CapabilityApi](../interfaces/capability.capabilityapi.md#interface-capabilityapi)

***Usage:***
These APIs return promises, not properties, and will need to be
asynchronously loaded by calling `get`.

```typescript
const [home, assets, offer] = await Promise.all([
  capabilityApi.get('home'),
  capabilityApi.get('assets'),
  capabilityApi.get('offer')
]);

```

API for fetching capability icon data.

## Index

### Enumerations

* [CapabilityIds](../enums/capabilityapi.capabilityids.md)
* [CapabilityNames](../enums/capabilityapi.capabilitynames.md)

### Interfaces

* [CapabilityApi](../interfaces/capabilityapi.capabilityapi-1.md)
* [CapabilityResponse](../interfaces/capabilityapi.capabilityresponse.md)
