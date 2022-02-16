**[@adobe/exc-app](../README.md)**

> [Globals](../README.md) / [cache](../modules/cache.md) / CacheApi

# Interface: CacheApi

APIs for managing a client side persisted cache.

## Hierarchy

* **CacheApi**

## Index

### Methods

* [delete](cache.cacheapi.md#delete)
* [get](cache.cacheapi.md#get)
* [set](cache.cacheapi.md#set)

## Methods

### delete

▸ **delete**(`params`: [CacheParameters](cache.cacheparameters.md)): Promise<void\>

Deletes a value from the cache (If available).

#### Parameters:

Name | Type | Description |
------ | ------ | ------ |
`params` | [CacheParameters](cache.cacheparameters.md) | Parameters used to identify the cached item to delete.  |

**Returns:** Promise<void\>

___

### get

▸ **get**<T\>(`params`: [CacheParameters](cache.cacheparameters.md)): Promise<[CacheEntry](../modules/cache.md#cacheentry)<T\> \| undefined\>

Gets a value from the cache if one is available.

#### Type parameters:

Name |
------ |
`T` |

#### Parameters:

Name | Type | Description |
------ | ------ | ------ |
`params` | [CacheParameters](cache.cacheparameters.md) | Parameters used to identify the cached item to retrieve. |

**Returns:** Promise<[CacheEntry](../modules/cache.md#cacheentry)<T\> \| undefined\>

A promise that resolves to the specified value, or undefined if none exist.

___

### set

▸ **set**<T\>(`params`: [CacheSetParameters](cache.cachesetparameters.md)<T\>): Promise<void\>

Stores a value in the cache.

#### Type parameters:

Name |
------ |
`T` |

#### Parameters:

Name | Type | Description |
------ | ------ | ------ |
`params` | [CacheSetParameters](cache.cachesetparameters.md)<T\> | Parameters used to identify the cached item to store and control its TTL.  |

**Returns:** Promise<void\>
