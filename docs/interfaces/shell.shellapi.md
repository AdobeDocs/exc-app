**[@adobe/exc-app](../README.md)**

> [Globals](../README.md) / [shell](../modules/shell.md) / ShellApi

# Interface: ShellApi

## Hierarchy

* EventEmitter<ShellInfoEvent\>

  ↳ **ShellApi**

## Index

### EventEmitter Methods

* [emit](shell.shellapi.md#emit)
* [off](shell.shellapi.md#off)
* [on](shell.shellapi.md#on)

### Other Methods

* [get](shell.shellapi.md#get)

## EventEmitter Methods

### emit

▸ **emit**<K\>(`type`: K, `event?`: ShellInfoEvent[K]): void

*Inherited from void*

Invoke all handlers for the given type.

#### Type parameters:

Name | Type |
------ | ------ |
`K` | keyof ShellInfoEvent |

#### Parameters:

Name | Type | Description |
------ | ------ | ------ |
`type` | K | The event type to invoke. |
`event?` | ShellInfoEvent[K] | Any value (object is recommended and powerful), passed to each handler. |

**Returns:** void

___

### off

▸ **off**<K\>(`type`: K, `handler`: (event?: ShellInfoEvent[K]) => void): void

*Inherited from void*

Remove an event handler for the given type.

#### Type parameters:

Name | Type |
------ | ------ |
`K` | keyof ShellInfoEvent |

#### Parameters:

Name | Type | Description |
------ | ------ | ------ |
`type` | K | Type of event to unregister `handler` from. |
`handler` | (event?: ShellInfoEvent[K]) => void | Handler function to remove. |

**Returns:** void

___

### on

▸ **on**<K\>(`type`: K, `handler`: (event?: ShellInfoEvent[K]) => void): void

*Inherited from void*

Register an event handler for the given type.

#### Type parameters:

Name | Type |
------ | ------ |
`K` | keyof ShellInfoEvent |

#### Parameters:

Name | Type | Description |
------ | ------ | ------ |
`type` | K | Type of event to listen for. |
`handler` | (event?: ShellInfoEvent[K]) => void | Function to call in response to given event. |

**Returns:** void

___

## Other Methods

### get

▸ **get**<T\>(`type`: T): Promise<ShellInfo[T]\>

Gets the specified type of information about the shell.

#### Type parameters:

Name | Type |
------ | ------ |
`T` | keyof [ShellInfo](shell.shellinfo.md) |

#### Parameters:

Name | Type | Description |
------ | ------ | ------ |
`type` | T | The type of information to get.  |

**Returns:** Promise<ShellInfo[T]\>
