**[@adobe/exc-app](../README.md)**

> [Globals](../README.md) / [root](../modules/root.md) / Runtime

# Interface: Runtime<T\>

Defines the runtime object providing all unified-shell APIs for solution authors.

## Type parameters

Name | Default |
------ | ------ |
`T` | Record<string, any\\> |

## Hierarchy

* EventEmitter

  ↳ **Runtime**

## Index

### EventEmitter Methods

* [emit](root.runtime.md#emit)
* [off](root.runtime.md#off)
* [on](root.runtime.md#on)

## EventEmitter Methods

### emit

▸ **emit**<K\>(`type`: K, `event?`: T[K]): void

*Inherited from void*

Invoke all handlers for the given type.

#### Type parameters:

Name | Type |
------ | ------ |
`K` | keyof T |

#### Parameters:

Name | Type | Description |
------ | ------ | ------ |
`type` | K | The event type to invoke. |
`event?` | T[K] | Any value (object is recommended and powerful), passed to each handler. |

**Returns:** void

___

### off

▸ **off**<K\>(`type`: K, `handler`: (event?: T[K]) => void): void

*Inherited from void*

Remove an event handler for the given type.

#### Type parameters:

Name | Type |
------ | ------ |
`K` | keyof T |

#### Parameters:

Name | Type | Description |
------ | ------ | ------ |
`type` | K | Type of event to unregister `handler` from. |
`handler` | (event?: T[K]) => void | Handler function to remove. |

**Returns:** void

___

### on

▸ **on**<K\>(`type`: K, `handler`: (event?: T[K]) => void): void

*Inherited from void*

Register an event handler for the given type.

#### Type parameters:

Name | Type |
------ | ------ |
`K` | keyof T |

#### Parameters:

Name | Type | Description |
------ | ------ | ------ |
`type` | K | Type of event to listen for. |
`handler` | (event?: T[K]) => void | Function to call in response to given event. |

**Returns:** void
