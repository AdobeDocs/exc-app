**[@adobe/exc-app](../README.md)**

> [Globals](../README.md) / session

# Module: session

APIs to get, set or invalidate session data. These APIs are meant for applications using their
own session management in addition Adobe IMS. These APIs are not meant to manage session but
rather cache and recycle them whenever possible.

To consume this API, add the following import to your code.

```typescript
import session from '@adobe/exc-app/session';
```

The default export is an object of type [SessionApi](../interfaces/_session_.sessionapi.md)

API reference: [scroll down](#index)

### Sample code

``` typescript
import session from '@adobe/exc-app/settings';

// Get
const session = await session.get();

// Set to expire an hour from now
await session.set({
  expires: Date.now() + 3600 * 1000,
  id: 'SESSION_ID'
});

// Invalidate session
const session = await session.get();
await session.invalidate(session);
```

## Index

### Enumerations

* [SessionScope](../enums/session.sessionscope.md)

### Interfaces

* [Session](../interfaces/session.session-1.md)
* [SessionApi](../interfaces/session.sessionapi.md)
