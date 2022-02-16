**[@adobe/exc-app](../README.md)**

> [Globals](../README.md) / [network](../modules/network.md) / QueryRequest

# Interface: QueryRequest

Query request interface.

## Hierarchy

* **QueryRequest**

## Index

### Properties

* [acceptLanguage](network.queryrequest.md#acceptlanguage)
* [appId](network.queryrequest.md#appid)
* [data](network.queryrequest.md#data)
* [maxRetries](network.queryrequest.md#maxretries)
* [metadata](network.queryrequest.md#metadata)
* [operationName](network.queryrequest.md#operationname)
* [preferredRegion](network.queryrequest.md#preferredregion)
* [regionEnabled](network.queryrequest.md#regionenabled)
* [routing](network.queryrequest.md#routing)
* [scope](network.queryrequest.md#scope)
* [statusCodesToRetry](network.queryrequest.md#statuscodestoretry)
* [totalFetchTime](network.queryrequest.md#totalfetchtime)

## Properties

### acceptLanguage

• `Optional` **acceptLanguage**: undefined \| string

Set the Accept-Language HTTP header in the request. Defaults to '*' (any language).

See https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Accept-Language for more details.

___

### appId

• `Optional` **appId**: undefined \| string

Overwrite config.appId until federation is out. This allow scenario where sharing components that are linked to their own tenants.

___

### data

•  **data**: [GraphQLQuery](network.graphqlquery.md) \| Array<[GraphQLQuery](network.graphqlquery.md)\>

Data containing single or multiple GQL queries.

***Example:***

```typescript
{data: {
  query: `
    query userBehanceQuery($userId: String!, $apiKey: String!) {
      userBehance(userId: $userId, apiKey: $apiKey) {
        images
      }
    }`,
  variables: {
    userId: '123@AdobeID',
    apiKey: 'test-app'
  }
 }
};
```

___

### maxRetries

• `Optional` **maxRetries**: undefined \| number

Number indicating how many fetch attempts should be made using exponential backoff.

___

### metadata

• `Optional` **metadata**: [DefaultMetaData](network.defaultmetadata.md)

default metadata should be given when you want to override the default metadata which will be passed with every request

___

### operationName

• `Optional` **operationName**: undefined \| string

Query ID- To analyze a query's metrics & performance.

***Example:***

```typescript
{operationName: 'BehanceAvatar'}
```

___

### preferredRegion

• `Optional` **preferredRegion**: [GraphQLRegion](../modules/network.md#graphqlregion)

Preferred region to send the GraphQL request to

___

### regionEnabled

• `Optional` **regionEnabled**: undefined \| false \| true

passed as true if someone wants to call the region specific endpoints directly.

___

### routing

• `Optional` **routing**: [ROUTING](../enums/network.routing.md)

Enable profile based routing

___

### scope

• `Optional` **scope**: [FetchScope](../enums/network.fetchscope.md)

Pass enum to set headers according to the requirements

___

### statusCodesToRetry

• `Optional` **statusCodesToRetry**: number[]

HTTP Status Codes which will prompt a retry. If not provided only network failures
will prompt a retry.

___

### totalFetchTime

• `Optional` **totalFetchTime**: undefined \| number

Number in ms indicating the maximum amount of time taken by the request plus any exponential backoff
requests before aborting.
