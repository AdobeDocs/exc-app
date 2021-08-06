**[@adobe/exc-app](../README.md)**

> [Globals](../README.md) / network

# Module: network

APIs that simplify code to make authenticated network requests for resources, execute GraphQL
queries, etc..

***Import:***

```typescript
import {fetch, query} from '@adobe/exc-app/network';
```

***Default export:***

[NetworkApi](../interfaces/network.networkapi.md)

***Usage:***

```typescript
import {fetch, query} from '@adobe/exc-app/network';

// Performs a window.fetch call with Authorization and x-api-key headers set
const fetchResponse = await fetch('https://localhost', {auth: 'Header', method: 'GET'});

// Executes a query for resources to the ExC GraphQL service
const queryResponse = await query({
  data: {
    query: `
      query userBehanceQuery($userId: String!, $apiKey: String!) {
        userBehance(userId: $userId, apiKey: $apiKey) {
          images
        }
      }`,
    variables: {
      apiKey: 'test-app',
      userId: '123@AdobeID'
    }
  },
  operationName: 'BehanceAvatar'
});

```

## Index

### Enumerations

* [FetchScope](../enums/network.fetchscope.md)
* [ROUTING](../enums/network.routing.md)

### Interfaces

* [DefaultMetaData](../interfaces/network.defaultmetadata.md)
* [FetchOptions](../interfaces/network.fetchoptions.md)
* [GraphQLQuery](../interfaces/network.graphqlquery.md)
* [NetworkApi](../interfaces/network.networkapi.md)
* [QueryRequest](../interfaces/network.queryrequest.md)

### Type aliases

* [FetchInit](network.md#fetchinit)

### Functions

* [fetch](network.md#fetch)
* [query](network.md#query)

## Type aliases

### FetchInit

Ƭ  **FetchInit**: RequestInit & [FetchOptions](../interfaces/network.fetchoptions.md)

Defines the object containing any custom settings that you want to apply to the request. You can
also additionally specify the 'auth' parameter to automatically set the Authentication, API key in Headers/Query params.

***Example:***

`{auth: 'Header', body: 'xyz', headers: {'Content-Type': 'text/plain'}, method: 'POST'}` or
`{auth: 'Header', method: 'GET'}` or
`{method: 'GET'}`

## Functions

### fetch

▸ **fetch**(`input`: RequestInfo, `init?`: [FetchInit](network.md#fetchinit)): Promise\<Response>

Provides an interface for fetching resources powered by the global 'fetch' API.

***Example:***

```typescript
// performs a window.fetch call
let response = await fetch('https://example.com/api/ping');

// performs a window.fetch call with Authorization and x-api-key headers set
response = await fetch('https://localhost', {auth: 'Header', method: 'GET'});

// performs a window.fetch call with user_token and client_id query parameters added to the URL
const request = new Request('https://localhost', {
  body: JSON.stringify({k: 'v'}),
  headers: new Headers(),
  method: 'POST'
});
response = await fetch(request, {auth: 'Header'});
```

#### Parameters:

Name | Type | Description |
------ | ------ | ------ |
`input` | RequestInfo | The resource that you wish to fetch. It can either be the URL of the resource you want to fetch or a Request object. |
`init?` | [FetchInit](network.md#fetchinit) | An object containing any custom settings that you want to apply to the request. |

**Returns:** Promise\<Response>

The promise for the response to the fetch operation.

___

### query

▸ **query**(`input`: [QueryRequest](../interfaces/network.queryrequest.md)): Promise\<Response>

Provides an interface for querying resources via GraphqQL.
In order to consume query, please make sure the respective query resolver is
available in the GraphQL Service.
***Example:***

```typescript
const BEHANCE_QUERY = `
  query userBehanceQuery($userId: String!, $apiKey: String!) {
    userBehance(userId: $userId, apiKey: $apiKey) {
      images
    }
  }`;

// queries the respective resource via GraphQL and returns HTTP Response {ok: true, status: 200, ...}
query({data: {query: BEHANCE_QUERY, variables: {
  userId: '123@AdobeID',
  apiKey: 'test-app',
}}, operationName: 'BehanceAvatar'});

// queries the respective resource via GraphQL and returns HTTP Response {ok: true, status: 200, ...}
query({data: {query: `
  query userBehanceQuery {
    userBehance(userId: "123@AdobeID", apiKey: "test-app") {
      images
    }
  }`
}});
```

#### Parameters:

Name | Type | Description |
------ | ------ | ------ |
`input` | [QueryRequest](../interfaces/network.queryrequest.md) | Query request containing desired GQL Query. |

**Returns:** Promise\<Response>

The promise for the response to the query operation.
