**[@adobe/exc-app](../README.md)**

> [Globals](../README.md) / [session](../modules/session.md) / SessionApi

# Interface: SessionApi

APIs to get, set or invalidate session data. These APIs are meant for applications using their
own session management in addition Adobe IMS. These APIs are not meant to manage session but
rather cache and recycle them whenever possible.

## Hierarchy

* **SessionApi**

## Index

### Methods

* [get](session.sessionapi.md#get)
* [invalidate](session.sessionapi.md#invalidate)
* [set](session.sessionapi.md#set)

## Methods

### get

▸ **get**(): Promise<[Session](session.session-1.md)\>

Gets a stored session if one is available.

**Returns:** Promise<[Session](session.session-1.md)\>

Session object

___

### invalidate

▸ **invalidate**(`session`: [Session](session.session-1.md)): Promise<void\>

Invalidates a session if its current.

#### Parameters:

Name | Type |
------ | ------ |
`session` | [Session](session.session-1.md) |

**Returns:** Promise<void\>

___

### set

▸ **set**(`session`: [Session](session.session-1.md)): Promise<void\>

Stores the current session

#### Parameters:

Name | Type |
------ | ------ |
`session` | [Session](session.session-1.md) |

**Returns:** Promise<void\>
