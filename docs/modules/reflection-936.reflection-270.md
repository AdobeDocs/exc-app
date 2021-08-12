**[@adobe/exc-app](../README.md)**

> [Globals](../README.md) / [](reflection-936.md) / 

# Module: 

## Index

### Interfaces

* [Modules](../interfaces/reflection-936.reflection-270.modules.md)
* [Runtime](../interfaces/reflection-936.reflection-270.runtime.md)

### Functions

* [init](reflection-936.reflection-270.md#init)
* [runtime](reflection-936.reflection-270.md#runtime)

## Functions

### init

▸ **init**(`bootstrap`: (runtime: [Runtime](../interfaces/reflection-936.reflection-270.runtime.md)) => void): void

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
`bootstrap` | (runtime: [Runtime](../interfaces/reflection-936.reflection-270.runtime.md)) => void | Callback used to bootstrap a solution. The runtime object is passed in as a parameter to this callback.  |

**Returns:** void

___

### runtime

▸ **runtime**(): [Runtime](../interfaces/reflection-936.reflection-270.runtime.md)

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

**Returns:** [Runtime](../interfaces/reflection-936.reflection-270.runtime.md)

The runtime object.
