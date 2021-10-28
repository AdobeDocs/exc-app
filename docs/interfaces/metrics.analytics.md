**[@adobe/exc-app](../README.md)**

> [Globals](../README.md) / [metrics](../modules/metrics.md) / Analytics

# Interface: Analytics

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

## Hierarchy

* **Analytics**

## Index

### Methods

* [track](metrics.analytics.md#track)
* [trackEvent](metrics.analytics.md#trackevent)
* [trackPage](metrics.analytics.md#trackpage)
* [trackUser](metrics.analytics.md#trackuser)

## Methods

### track

▸ **track**(`type`: \"event\" \| \"page\" \| \"user\", ...`args`: any): void

Complements the corresponding window._satellite.track() method and records an Analytics record.

#### Parameters:

Name | Type | Description |
------ | ------ | ------ |
`type` | \"event\" \| \"page\" \| \"user\" | The type of event. |
`...args` | any | Additional data to log.  |

**Returns:** void

___

### trackEvent

▸ **trackEvent**(`eventData`: Record<string, any\>): void

Set `window.digialData.eventData` to the specified input and record an Analytics record.

#### Parameters:

Name | Type |
------ | ------ |
`eventData` | Record<string, any\> |

**Returns:** void

___

### trackPage

▸ **trackPage**(`pageData`: Record<string, any\>): void

Set `window.digialData.pageData` to the specified input and record an Analytics record.

#### Parameters:

Name | Type | Description |
------ | ------ | ------ |
`pageData` | Record<string, any\> | The object to assign to `window.digitalData.pageData`.  |

**Returns:** void

___

### trackUser

▸ **trackUser**(`userData`: Record<string, any\>): void

Set `window.digialData.userData` to the specified input and record an Analytics record.

#### Parameters:

Name | Type | Description |
------ | ------ | ------ |
`userData` | Record<string, any\> | The object to assign to `window.digitalData.userData`.  |

**Returns:** void
