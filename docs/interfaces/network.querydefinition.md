**[@adobe/exc-app](../README.md)**

> [Globals](../README.md) / [network](../modules/network.md) / QueryDefinition

# Interface: QueryDefinition

Defines a GraphQL query that will be executed to fetch the data exposed by this contract.

## Hierarchy

* [GraphQLQuery](network.graphqlquery.md)

  ↳ **QueryDefinition**

## Index

### Properties

* [dataPath](network.querydefinition.md#datapath)
* [fetchScope](network.querydefinition.md#fetchscope)
* [ignoreErrorsOnPaths](network.querydefinition.md#ignoreerrorsonpaths)
* [query](network.querydefinition.md#query)
* [variables](network.querydefinition.md#variables)

## Properties

### dataPath

• `Optional` **dataPath**: undefined \| string

When provided, the data at the certain path will be returned.
If not provided, the entire GraphQL response will be returned.

___

### fetchScope

•  **fetchScope**: [FetchScope](../enums/network.fetchscope.md)

Fetch scope. Controls which headers are sent with the query.
See fetch documentation for more info.

___

### ignoreErrorsOnPaths

• `Optional` **ignoreErrorsOnPaths**: string[]

Do not fail (throw) when encountering errors while processing the query if the errors
happened on certain paths.

___

### query

•  **query**: string

*Inherited from [GraphQLQuery](network.graphqlquery.md).[query](network.graphqlquery.md#query)*

GQL Query.

***Example:***

```typescript
{query: `
  query userBehanceQuery($userId: String!, $apiKey: String!) {
    userBehance(userId: $userId, apiKey: $apiKey) {
      images
    }
  }`
};

{query: `
  query userBehanceQuery {
    userBehance(userId: "123@AdobeID", apiKey: "test-app") {
      images
    }
  }`
};
```

___

### variables

• `Optional` **variables**: Record<string, any\>

*Inherited from [GraphQLQuery](network.graphqlquery.md).[variables](network.graphqlquery.md#variables)*

Query specific variables- key value pairs.

***Example:***

```typescript
{variables: {
  apiKey: 'test-app',
  userId: '123@AdobeID'
 }
};
```
