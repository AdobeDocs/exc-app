**[@adobe/exc-app](../README.md)**

> [Globals](../README.md) / [metrics](../modules/metrics.md) / Metric

# Interface: Metric

Defines the attribute of a metric to be logged.

## Hierarchy

* **Metric**

## Index

### Properties

* [counter](metrics.metric.md#counter)
* [data](metrics.metric.md#data)
* [event](metrics.metric.md#event)
* [level](metrics.metric.md#level)
* [message](metrics.metric.md#message)
* [recordType](metrics.metric.md#recordtype)

## Properties

### counter

• `Optional` **counter**: undefined \| number

A long integer storage column, e.g. the value when recordType = Counter.

___

### data

• `Optional` **data**: any

An opaque (to Metrics) object for application storage.

___

### event

• `Optional` **event**: string \| string[]

An application-defined event.

___

### level

• `Optional` **level**: Level

The importance of this metric, e.g. log level.

___

### message

• `Optional` **message**: undefined \| string

A human-readable message, e.g. console messages.

___

### recordType

• `Optional` **recordType**: undefined \| string

The type of this metric record, may be application-specific.
