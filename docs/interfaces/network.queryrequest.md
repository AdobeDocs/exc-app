**[@adobe/exc-app](../README.md)**

> [Globals](../README.md) / [network](../modules/network.md) / QueryRequest

# Interface: QueryRequest

Query request interface.

## Hierarchy

* **QueryRequest**

## Index

### Properties

* [appId](network.queryrequest.md#appid)
* [data](network.queryrequest.md#data)
* [excludeSandbox](network.queryrequest.md#excludesandbox)
* [maxRetries](network.queryrequest.md#maxretries)
* [metadata](network.queryrequest.md#metadata)
* [operationName](network.queryrequest.md#operationname)
* [regionEnabled](network.queryrequest.md#regionenabled)
* [routing](network.queryrequest.md#routing)
* [scope](network.queryrequest.md#scope)
* [totalFetchTime](network.queryrequest.md#totalfetchtime)

## Properties

### appId

• `Optional` **appId**: undefined \| string

Overwrite config.appId until federation is out. This allow scenario where sharing components that are linked to their own tenants.

___

### data

•  **data**: [GraphQLQuery](network.graphqlquery.md) \| Array\<[GraphQLQuery](network.graphqlquery.md)>

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

### excludeSandbox

• `Optional` **excludeSandbox**: undefined \| false \| true

Whether or not to exclude sandbox headers.

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

### totalFetchTime

• `Optional` **totalFetchTime**: undefined \| number

Number in ms indicating the maximum amount of time taken by the request plus any exponential backoff
requests before aborting.
