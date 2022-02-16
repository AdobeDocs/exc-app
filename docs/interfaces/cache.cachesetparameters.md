**[@adobe/exc-app](../README.md)**

> [Globals](../README.md) / [cache](../modules/cache.md) / CacheSetParameters

# Interface: CacheSetParameters<T\>

Input parameters for the Cache set API.

## Type parameters

Name |
------ |
`T` |

## Hierarchy

* [CacheParameters](cache.cacheparameters.md)

  ↳ **CacheSetParameters**

## Index

### Properties

* [expiry](cache.cachesetparameters.md#expiry)
* [key](cache.cachesetparameters.md#key)
* [scope](cache.cachesetparameters.md#scope)
* [value](cache.cachesetparameters.md#value)

## Properties

### expiry

• `Optional` **expiry**: [CacheExpiry](../modules/cache.md#cacheexpiry)

Cache expiry. Can be one of the set values defined by CacheTTL, or a numeric cache ttl (in seconds).
Optional - Defaults to one week.

___

### key

•  **key**: string

*Inherited from [CacheParameters](cache.cacheparameters.md).[key](cache.cacheparameters.md#key)*

Cache key.

___

### scope

• `Optional` **scope**: CacheScope

*Inherited from [CacheParameters](cache.cacheparameters.md).[scope](cache.cacheparameters.md#scope)*

Cache scope (Optional - Defaults to user).

___

### value

•  **value**: T

Data to cache. Data must be serializable (JSON).
