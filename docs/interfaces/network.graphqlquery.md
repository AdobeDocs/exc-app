**[@adobe/exc-app](../README.md)**

> [Globals](../README.md) / [network](../modules/network.md) / GraphQLQuery

# Interface: GraphQLQuery

GQL Query containing graphql query and variables.

## Hierarchy

* **GraphQLQuery**

  ↳ [QueryDefinition](network.querydefinition.md)

## Index

### Properties

* [query](network.graphqlquery.md#query)
* [variables](network.graphqlquery.md#variables)

## Properties

### query

•  **query**: string

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

Query specific variables- key value pairs.

***Example:***

```typescript
{variables: {
  apiKey: 'test-app',
  userId: '123@AdobeID'
 }
};
```
