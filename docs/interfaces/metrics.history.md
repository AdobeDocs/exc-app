**[@adobe/exc-app](../README.md)**

> [Globals](../README.md) / [metrics](../modules/metrics.md) / History

# Interface: History

Defines APIs used to log history events.

## Hierarchy

* **History**

## Index

### Methods

* [push](metrics.history.md#push)
* [replace](metrics.history.md#replace)

## Methods

### push

▸ **push**(`path`: string, `state?`: any, ...`args`: any): void

Records a history push event.

#### Parameters:

Name | Type | Description |
------ | ------ | ------ |
`path` | string | The current URL. |
`state?` | any | Optional. The state associated to the event. |
`...args` | any | - |

**Returns:** void

___

### replace

▸ **replace**(`path`: string, `state?`: any, ...`args`: any): void

Records a history replace event.

#### Parameters:

Name | Type | Description |
------ | ------ | ------ |
`path` | string | The current URL. |
`state?` | any | Optional. The state associated to the event. |
`...args` | any | - |

**Returns:** void
