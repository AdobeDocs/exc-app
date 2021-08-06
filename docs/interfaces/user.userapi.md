**[@adobe/exc-app](../README.md)**

> [Globals](../README.md) / [user](../modules/user.md) / UserApi

# Interface: UserApi

## Hierarchy

* EventEmitter\<UserInfoEvent>

  ↳ **UserApi**

## Index

### Properties

* [logoutUrl](user.userapi.md#logouturl)
* [showLanguagePicker](user.userapi.md#showlanguagepicker)

### EventEmitter Methods

* [emit](user.userapi.md#emit)
* [off](user.userapi.md#off)
* [on](user.userapi.md#on)

### Other Methods

* [authExpired](user.userapi.md#authexpired)
* [get](user.userapi.md#get)

## Properties

### logoutUrl

•  **logoutUrl**: string \| undefined

Optional. When specified this URL will be invoked upon user logging out. This is useful to
reduce the number of lingering sessions for solutions who have their own sessions server
(in addition to IMS).

___

### showLanguagePicker

•  **showLanguagePicker**: boolean \| undefined

If language picker should be opened.

## EventEmitter Methods

### emit

▸ **emit**\<K>(`type`: K, `event?`: UserInfoEvent[K]): void

*Inherited from void*

Invoke all handlers for the given type.

#### Type parameters:

Name | Type |
------ | ------ |
`K` | keyof UserInfoEvent |

#### Parameters:

Name | Type | Description |
------ | ------ | ------ |
`type` | K | The event type to invoke. |
`event?` | UserInfoEvent[K] | Any value (object is recommended and powerful), passed to each handler. |

**Returns:** void

___

### off

▸ **off**\<K>(`type`: K, `handler`: (event?: UserInfoEvent[K]) => void): void

*Inherited from void*

Remove an event handler for the given type.

#### Type parameters:

Name | Type |
------ | ------ |
`K` | keyof UserInfoEvent |

#### Parameters:

Name | Type | Description |
------ | ------ | ------ |
`type` | K | Type of event to unregister `handler` from. |
`handler` | (event?: UserInfoEvent[K]) => void | Handler function to remove. |

**Returns:** void

___

### on

▸ **on**\<K>(`type`: K, `handler`: (event?: UserInfoEvent[K]) => void): void

*Inherited from void*

Register an event handler for the given type.

#### Type parameters:

Name | Type |
------ | ------ |
`K` | keyof UserInfoEvent |

#### Parameters:

Name | Type | Description |
------ | ------ | ------ |
`type` | K | Type of event to listen for. |
`handler` | (event?: UserInfoEvent[K]) => void | Function to call in response to given event. |

**Returns:** void

___

## Other Methods

### authExpired

▸ **authExpired**(): void

API to notify the unified shell that APIs are returning 401 and user needs to be
re-authenticated.

**Returns:** void

___

### get

▸ **get**\<T>(`type`: T): Promise\<UserInfo[T]>

Gets the specified type of information about an user.

#### Type parameters:

Name | Type |
------ | ------ |
`T` | keyof [UserInfo](user.userinfo.md) |

#### Parameters:

Name | Type | Description |
------ | ------ | ------ |
`type` | T | The type of information to get.  |

**Returns:** Promise\<UserInfo[T]>
