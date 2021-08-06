**[@adobe/exc-app](../README.md)**

> [Globals](../README.md) / [metrics](../modules/metrics.md) / Timer

# Interface: Timer

Defines APIs on a timer.

## Hierarchy

* **Timer**

## Index

### Methods

* [time](metrics.timer.md#time)

## Methods

### time

▸ **time**(`event`: string \| { event: string  }, ...`args`: any): number

Records the elapsed time from when the timer was created by calling Metrics.start API.

#### Parameters:

Name | Type | Description |
------ | ------ | ------ |
`event` | string \| { event: string  } | The name of the event being logged. The `{event: string}` form of this argument can be used to specify the precise event name that should be recorded (the prefix supplied at construction time is ignored). |
`...args` | any | - |

**Returns:** number

The elapsed time since the timer started, in milliseconds.
