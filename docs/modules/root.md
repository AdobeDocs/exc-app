**[@adobe/exc-app](../README.md)**

> [Globals](../README.md) / root

# Module: root

API used to integrate as solution web application with the unified shell of the Adobe Experience
Cloud.

## Index

### References

* [RuntimeConfiguration](root.md#runtimeconfiguration)

### Interfaces

* [Modules](../interfaces/root.modules.md)
* [Poller](../interfaces/root.poller.md)
* [PollerHandle](../interfaces/root.pollerhandle.md)
* [PollingConfiguration](../interfaces/root.pollingconfiguration.md)
* [Runtime](../interfaces/root.runtime.md)
* [RuntimeConfiguration](../interfaces/root.runtimeconfiguration.md)
* [UserActivityEmitter](../interfaces/root.useractivityemitter.md)
* [UserActivityMonitor](../interfaces/root.useractivitymonitor.md)

### Functions

* [init](root.md#init)
* [runtime](root.md#runtime)

## References

### RuntimeConfiguration

Re-exports: [RuntimeConfiguration](../interfaces/root.runtimeconfiguration.md)

## Functions

### init

▸ **init**(`bootstrap`: (runtime: [Runtime](../interfaces/root.runtime.md)) => void): void

Initializes a solution web application by invoking the bootstrap callback
once the runtime is ready.
1. if the module is already defined, start to bootstrap
2. otherwise define the global callback that will be called when runtime is ready.

***Example:***

```typescript
import React from 'react';
import ReactDOM from 'react-dom';
import runtime, {init} from '@adobe/exc-app';

init(() => {
  ReactDOM.render(<MainComponent runtime={runtime()} />, document.querySelector('#main'));
});
```

#### Parameters:

Name | Type | Description |
------ | ------ | ------ |
`bootstrap` | (runtime: [Runtime](../interfaces/root.runtime.md)) => void | Callback used to bootstrap a solution. The runtime object is passed in as a parameter to this callback.  |

**Returns:** void

___

### runtime

▸ **runtime**(): [Runtime](../interfaces/root.runtime.md)

Get the runtime object which contains all unified-shell APIs.

***Example:***

```typescript
import React from 'react';
import ReactDOM from 'react-dom';
import excApp from '@adobe/exc-app';

export class MyComponent extends React.Component {
  constructor(props) {
    this.runtime = excApp();
  }
}
```

**Returns:** [Runtime](../interfaces/root.runtime.md)

The runtime object.
