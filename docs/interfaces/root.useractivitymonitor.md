**[@adobe/exc-app](../README.md)**

> [Globals](../README.md) / [root](../modules/root.md) / UserActivityMonitor

# Interface: UserActivityMonitor<T\>

## Type parameters

Name | Default |
------ | ------ |
`T` | Record<string, any\\> |

## Hierarchy

* EventEmitter

  ↳ **UserActivityMonitor**

## Index

### Properties

* [active](root.useractivitymonitor.md#active)
* [configure](root.useractivitymonitor.md#configure)
* [hidden](root.useractivitymonitor.md#hidden)
* [lastActive](root.useractivitymonitor.md#lastactive)

### EventEmitter Methods

* [emit](root.useractivitymonitor.md#emit)
* [off](root.useractivitymonitor.md#off)
* [on](root.useractivitymonitor.md#on)

### Other Methods

* [registerActivityEmitter](root.useractivitymonitor.md#registeractivityemitter)

## Properties

### active

•  **active**: boolean

___

### configure

•  **configure**: (config: [PollingConfiguration](root.pollingconfiguration.md)) => void

___

### hidden

•  **hidden**: boolean

___

### lastActive

•  **lastActive**: number

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

___

## Other Methods

### registerActivityEmitter

▸ **registerActivityEmitter**(`emitter`: [UserActivityEmitter](root.useractivityemitter.md)): void

#### Parameters:

Name | Type |
------ | ------ |
`emitter` | [UserActivityEmitter](root.useractivityemitter.md) |

**Returns:** void
