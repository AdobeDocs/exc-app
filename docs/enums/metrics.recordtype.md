**[@adobe/exc-app](../README.md)**

> [Globals](../README.md) / [metrics](../modules/metrics.md) / RecordType

# Enumeration: RecordType

RecordType is an enumeration of known telemetry records. These
record types have specified symantics and use specific columns
for each type. That said, any record type may specify any of the
known fields for the custom purpose of the application.

All RecordTypes except User are implementations of the Metric
interface. The User RecordType is for User context changes and should
not be created direclty by clients.

Clients may specify custom record types, however there will be no
attempt to validate any fields. Storage of custom record types may
silently fail.

## Index

### Enumeration members

* [ANALYTICS](metrics.recordtype.md#analytics)
* [EVENT](metrics.recordtype.md#event)
* [HISTORY](metrics.recordtype.md#history)
* [LOCATION](metrics.recordtype.md#location)
* [LOG](metrics.recordtype.md#log)
* [NAVIGATION\_TIMING](metrics.recordtype.md#navigation_timing)
* [NETWORK\_REQUEST](metrics.recordtype.md#network_request)
* [NETWORK\_RESPONSE](metrics.recordtype.md#network_response)
* [PAINT\_TIMING](metrics.recordtype.md#paint_timing)
* [RECENT](metrics.recordtype.md#recent)
* [RESOURCE\_TIMING](metrics.recordtype.md#resource_timing)
* [TIMER](metrics.recordtype.md#timer)
* [TRACER](metrics.recordtype.md#tracer)
* [USER](metrics.recordtype.md#user)

## Enumeration members

### ANALYTICS

•  **ANALYTICS**:  = "Analytics"

Analytics record type reports an Omega analtycis record. The dynamicData
object is copied from global.dynamicData.

___

### EVENT

•  **EVENT**:  = "Event"

Event reports an event to the system. Events are typically application-
specific enumerations. Event strings should be very stable since they
will be used for dashboards and alert queries. The recommended pattern is
to use featureArea.subject.verb, for example: shell.solutionPicker.click.

All events starting with 'exc.metrics' are reserved for metrics system use.

Event record types are very similar to Log record types with the main
difference being that the Event is expected to have a value for the event
property, and the message property is considered optional, whereas Log
records are expected to have a human-readable string in the message
property, and the event property is considered optional.

___

### HISTORY

•  **HISTORY**:  = "History"

History reports a history change in the current window. The
window.location object will be stored in metricsState.

___

### LOCATION

•  **LOCATION**:  = "Location"

Location reports a location change in the current window. Location
records should be emitted just prior to calling window location
methods to allow for flushing in case of reload. A
new historyId will be generated, and the page will be considered
'loading'.

___

### LOG

•  **LOG**:  = "Log"

Log RecordType reports a string message at a specified log level.
A logger name is optional but highly recommended for searching
and filtering since the log message can be any string.

___

### NAVIGATION\_TIMING

•  **NAVIGATION\_TIMING**:  = "NavigationTiming"

NavigationTiming reports the timing results of navigation events
emitted from the javascript VM. The NavigationTiming object is stored
in the metric's data property.

___

### NETWORK\_REQUEST

•  **NETWORK\_REQUEST**:  = "NetworkRequest"

NetworkRequest reports the start of a network invocation, including
the url and request parameters. The metric's data property will
contain the network Request object supplied by the javascript VM.

___

### NETWORK\_RESPONSE

•  **NETWORK\_RESPONSE**:  = "NetworkResponse"

NetworkResponse reports the conclusion of a network invocation, which
may be an HTTP status or an outright error. The metric's data
property will contain either the Response object from the
javascritp VM, or the Error returned by the network call.

___

### PAINT\_TIMING

•  **PAINT\_TIMING**:  = "PaintTiming"

PaintTiming reports the paint timing results as supplied by
the Performance interface from the javascript VM. The PaintTiming
object is stored in the metric's data property.

___

### RECENT

•  **RECENT**:  = "Recent"

Recent is an Event destined for collection by the Unified Recents team.
The data bag is expected to be prescribed yet customized for this record
type and may contain PII. As such, the payload is ingested as a Log metric
with User data. The Gateway sends the RECENT event to Unified Recents then
sends the sanitized record to ADX.

___

### RESOURCE\_TIMING

•  **RESOURCE\_TIMING**:  = "ResourceTiming"

ResourceTiming reports the timing results of network resource requests
as reported by the Performance interface. The metric's data property
will contain the ResourceTiming object suppolied by the javascript VM.

___

### TIMER

•  **TIMER**:  = "Timer"

Timer reports the elapsed time between events. The duration property
records the elapsed time since construction - the timer "starts" at
construction. Timers are typically constructed using the start()
method on an instance of Metrics. It is also possible to construct
a new Timer object direclty, in which case a logger-style name for
the timer is highly recommended to aid searching and filtering.

___

### TRACER

•  **TRACER**:  = "Tracer"

Tracer is a reserved RecordType for monitoring system health. It should
not be used by clients.

___

### USER

•  **USER**:  = "User"

The User RecordType reports changes in the current user's login
status and current effective group. This record type should not
be used direclty. Instead, use the setUser() and clearUser()
methods.
