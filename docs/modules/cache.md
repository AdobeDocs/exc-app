**[@adobe/exc-app](../README.md)**

> [Globals](../README.md) / cache

# Module: cache

APIs for managing a client side persisted cache.
Unified Shell will store the data against its own domain, which allows data caching
even when the actual app runs on a domain which is 3rd party to Unified Shell's.

For example, the API will work in Chrome incognito when Unified Shell runs on an adobe.com domain
and the embedded applications run on the adobe.net domain.

These APIs utilizes the [Browser Cache API](https://developer.mozilla.org/en-US/docs/Web/API/Cache) under the hood and are all run asynchronously.

If migrating from Local Storage to Cache API, make sure all the app logic is async first.

NOTE: This API should not be used to cache any PII data to comply with Adobe privacy policies.

To consume this API, add the following import to your code.

```typescript
import cache from '@adobe/exc-app/cache';
```

The default export is an object of type [CacheAPI](../interfaces/_cache_.cacheapi.md)

API reference: [scroll down](#index)

### Sample code

```typescript
import cache, {CacheTTL, CacheScope} from '@adobe/exc-app/cache';

// By default, cached data is tied to the user and cached for a week.
await cache.set<MyType>({key: 'some-cache-key', value: myTypeInstance});

// Both scope and expiry can be adjusted.
await cache.set<MyType>({key: 'some-cache-key', value: myTypeInstance, expiry: CacheTTL.DAY, scope: CacheScope.ORG});

// It is also possible to bind cache data to the current IMS session, it will expire when the user logs out.
await cache.set<MyType>({key: 'some-cache-key', value: myTypeInstance, expiry: CacheTTL.IMS_SESSION});

// Cache get
const myData: MyType = await cache.get<MyType>({key: 'some-cache-key'});

// Get scope must be identical to the scope used for set - Always use the same scope for both.
const myData2: MyType = await cache.get<MyType>({key: 'some-cache-key', scope: CacheScope.ORG});

// Cache delete.
await cache.delete({key: 'some-cache-key'});
```

## Index

### Interfaces

* [CacheApi](../interfaces/cache.cacheapi.md)
* [CacheParameters](../interfaces/cache.cacheparameters.md)
* [CacheSetParameters](../interfaces/cache.cachesetparameters.md)

### Type aliases

* [CacheEntry](cache.md#cacheentry)
* [CacheExpiry](cache.md#cacheexpiry)

## Type aliases

### CacheEntry

Ƭ  **CacheEntry**<T\>: { createdAt: number ; key: string ; value: T  } & { expiresAt: number  } \| { expireBySession: true  }

Cache entry (Returned by the get API).

#### Type parameters:

Name |
------ |
`T` |

___

### CacheExpiry

Ƭ  **CacheExpiry**: CacheTTL \| number
