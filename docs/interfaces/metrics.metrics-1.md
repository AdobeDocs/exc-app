**[@adobe/exc-app](../README.md)**

> [Globals](../README.md) / [metrics](../modules/metrics.md) / Metrics

# Interface: Metrics

Defines metrics APIs.

## Hierarchy

* **Metrics**

## Index

### Properties

* [analytics](metrics.metrics-1.md#analytics)
* [history](metrics.metrics-1.md#history)

### Methods

* [debug](metrics.metrics-1.md#debug)
* [error](metrics.metrics-1.md#error)
* [event](metrics.metrics-1.md#event)
* [info](metrics.metrics-1.md#info)
* [log](metrics.metrics-1.md#log)
* [recent](metrics.metrics-1.md#recent)
* [start](metrics.metrics-1.md#start)
* [store](metrics.metrics-1.md#store)
* [warn](metrics.metrics-1.md#warn)

## Properties

### analytics

•  **analytics**: Readonly<[Analytics](metrics.analytics.md)\>

The Analytics APIs are designed to mirror the Omega APIs, enabling an Analtyics record to be
remotely stored which simulatenously captures additional context provided by the Metrics system
at the same time that window.digitalData is sent to analytics. Two use cases are supported,
described as follows.

For applications that provide Omega launch script configuration to the
`MetricsBrowserRuntime.init()` method, the corresponding portions of the digitalData object can
be supplied to the following APIs, and the Metrics SDK will store the provided object in
`window.digitalData`, and simultaneously record the Analytics record in remote storage and call
the Omega `window._satellite.track()` method. This approach assures consistency in the data
between Omega and Metrics.

___

### history

•  **history**: Readonly<[History](metrics.history.md)\>

The History APIs are designed to mirror browser history management. Calling a Metrics history
API is recommended either immediately before or after a call to window history, and will record
a History record type and begin a new page load by generating a new HistoryID guid.

## Methods

### debug

▸ **debug**(`message`: string, ...`args`: any): void

Log a debug message similar to console.debug().

#### Parameters:

Name | Type | Description |
------ | ------ | ------ |
`message` | string | The message being logged. |
`...args` | any | Additional data associated to the log entry.  |

**Returns:** void

___

### error

▸ **error**(`message`: string, ...`args`: any): void

Log an error message similar to console.error().

#### Parameters:

Name | Type | Description |
------ | ------ | ------ |
`message` | string | The message being logged. |
`...args` | any | Additional data associated to the error.  |

**Returns:** void

___

### event

▸ **event**(`event`: string \| string[], ...`args`: any): void

Records the specified event.

#### Parameters:

Name | Type | Description |
------ | ------ | ------ |
`event` | string \| string[] | The name of the event being logged. |
`...args` | any | - |

**Returns:** void

___

### info

▸ **info**(`message`: string, ...`args`: any): void

Log an informational message similar to console.info().

#### Parameters:

Name | Type | Description |
------ | ------ | ------ |
`message` | string | The message being logged. |
`...args` | any | Additional data associated to the log entry.  |

**Returns:** void

___

### log

▸ **log**(`message`: string, `args`: any): void

Log an informational message similar to console.log().

#### Parameters:

Name | Type | Description |
------ | ------ | ------ |
`message` | string | The message being logged. |
`args` | any | Additional data associated to the log entry.  |

**Returns:** void

___

### recent

▸ **recent**(`revent`: string \| string[], ...`args`: any): void

Construct a named "Recent" event and emit it to storage. The payload is expected
to contain PII so downstream handling must a) keep the data bag intact, and
b) send the Recent record (with PII) only to Unified Recents. PII must be
removed before sending to ADX.

**`function`** 

#### Parameters:

Name | Type | Description |
------ | ------ | ------ |
`revent` | string \| string[] | The event. |
`...args` | any | Optional arguments to be applied to the recorded metrics. |

**Returns:** void

A promise that resolves to the number of metrics that
were queued for eventual flushing.

___

### start

▸ **start**(`name`: string, ...`args`: any): [Timer](metrics.timer.md)

Starts a named timer that can be used to record time taken for an operation.

#### Parameters:

Name | Type | Description |
------ | ------ | ------ |
`name` | string | The name for the timer, which is used as a prefix for the emitted timer events. |
`...args` | any | Additional data associated to the timer.  |

**Returns:** [Timer](metrics.timer.md)

___

### store

▸ **store**(`metric`: [Metric](metrics.metric.md)): void

Stores the specified metric entry.

#### Parameters:

Name | Type | Description |
------ | ------ | ------ |
`metric` | [Metric](metrics.metric.md) | The metric to be logged.  |

**Returns:** void

___

### warn

▸ **warn**(`message`: string, ...`args`: any): void

Log a warning message similar to console.warn().

#### Parameters:

Name | Type | Description |
------ | ------ | ------ |
`message` | string | The message being logged. |
`...args` | any | Additional data associated to the log entry.  |

**Returns:** void
