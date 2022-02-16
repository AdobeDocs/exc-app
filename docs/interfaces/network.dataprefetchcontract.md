**[@adobe/exc-app](../README.md)**

> [Globals](../README.md) / [network](../modules/network.md) / DataPrefetchContract

# Interface: DataPrefetchContract<T\>

Defines a data contract which will be executed by Unified Shell on behalf ot the requesting application.

## Type parameters

Name |
------ |
`T` |

## Hierarchy

* **DataPrefetchContract**

## Index

### Properties

* [defaultValue](network.dataprefetchcontract.md#defaultvalue)
* [expiry](network.dataprefetchcontract.md#expiry)
* [fetchWhen](network.dataprefetchcontract.md#fetchwhen)
* [gql](network.dataprefetchcontract.md#gql)
* [isSensitive](network.dataprefetchcontract.md#issensitive)
* [key](network.dataprefetchcontract.md#key)
* [refreshData](network.dataprefetchcontract.md#refreshdata)
* [revalidate](network.dataprefetchcontract.md#revalidate)
* [scope](network.dataprefetchcontract.md#scope)
* [shared](network.dataprefetchcontract.md#shared)

## Properties

### defaultValue

•  **defaultValue**: T

Default value to return if the data execution is skipped.

___

### expiry

•  **expiry**: [CacheExpiry](../modules/cache.md#cacheexpiry)

Cache expiry. Can be one of the set values defined by the Cache API, or a numeric cache ttl (in seconds).

___

### fetchWhen

• `Optional` **fetchWhen**: [FetchCondition](network.fetchcondition.md)

Defines the conditions when certain data can be fetched.
When conditions are not met, the default value above will be returned (But not cached).

___

### gql

• `Optional` **gql**: [QueryDefinition](network.querydefinition.md)

GraphQL used to fulfill this data contract.
Note: Currently GraphQL is the only supported method for data contracts.

___

### isSensitive

•  **isSensitive**: boolean

Is the data sensitive? (PII or other sensitive data).
Sensitive data can only be cached in the browser's session storage
Non-sensitive data can be cached in the standard Cache storage.

___

### key

•  **key**: string

Unique key associated with this contract.
Will be used by the calling application to get access to the data.

___

### refreshData

• `Optional` **refreshData**: undefined \| { dedup?: [DataDedupConfig](network.datadedupconfig.md) ; gql?: [QueryDefinition](network.querydefinition.md) ; keepOriginal?: string[]  }

Defines specific behavior for refresh.
This is optional, by default refreshing data and fetching new will yield the same results.

___

### revalidate

•  **revalidate**: { enabled: boolean ; immediate?: undefined \| false \| true ; revalidateAfterSec?: undefined \| number  }

When true, data will be fetched even when a cache is available.
In this case, the query will return the cached data and at the same time fetch fresh data from the network.
(stale-while-revalidate strategy)

#### Type declaration:

Name | Type | Description |
------ | ------ | ------ |
`enabled` | boolean | When true, data will be fetched even when a cache is available. In this case, the query will return the cached data and at the same time fetch fresh data from the network. (stale-while-revalidate strategy) |
`immediate?` | undefined \| false \| true | If true, revalidation will be done right away If false, revalidation will be done when the browser is idle (On browsers where requestIdleCallback is supported, otherwise right away) Optional - Defaults to false |
`revalidateAfterSec?` | undefined \| number | Used in conjunction with revalidate = true. Threshold for revalidating data from the network. When set the query will return the cached data and if the cache is older than the set threshold, fetch fresh data from the network. Optional - Defaults to 0 (immediate) |

___

### scope

•  **scope**: CacheScope

Cache scope as defined by the Cache API.

___

### shared

•  **shared**: boolean

If true, this data will be accessible to all experience cloud applications.
Otherwise, data will be cached against the requesting application.
