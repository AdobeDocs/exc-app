**[@adobe/exc-app](../README.md)**

> [Globals](../README.md) / [network](../modules/network.md) / NetworkApi

# Interface: NetworkApi

## Hierarchy

* **NetworkApi**

## Index

### Methods

* [fetch](network.networkapi.md#fetch)
* [query](network.networkapi.md#query)

## Methods

### fetch

▸ **fetch**(`input`: RequestInfo, `init?`: [FetchInit](../modules/network.md#fetchinit)): Promise\<Response>

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
`init?` | [FetchInit](../modules/network.md#fetchinit) | An object containing any custom settings that you want to apply to the request. |

**Returns:** Promise\<Response>

The promise for the response to the fetch operation.

___

### query

▸ **query**(`request`: [QueryRequest](network.queryrequest.md)): Promise\<Response>

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
`request` | [QueryRequest](network.queryrequest.md) | Query request containing desired GQL Query. |

**Returns:** Promise\<Response>

The promise for the response to the query operation.
