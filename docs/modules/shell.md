**[@adobe/exc-app](../README.md)**

> [Globals](../README.md) / shell

# Module: shell

API to request shell-specific information such as environment and shellInfo.

***Import:***

```typescript
import shell from '@adobe/exc-app/shell';
```

***Default export:***

[ShellApi](../interfaces/shell.shellapi.md#interface-shellapi)

***Usage:***

Below is an example of how to get various attributes associated to the shell:

```typescript
import shell from '@adobe/exc-app/shell';

const [env, imsEnv, info] = await Promise.all([
  shell.get('environment'),
  shell.get('imsEnvironment'),
  shell.get('shellInfo')
]);
```

### Receiving updates

You can also listen for updates on the requested data by listening to specific change events.

These change events are emitted from the api that the data is requested from. For example, if a
shell calls `await shell.get('shellInfo');` they must listen for the change event on
`shell.on('change:shellInfo')`. If a shell calls `await shell.get('environment')` they must listen for the
change event on `shell.on('change:environment')`. Here is a more detailed example of how the promise
api and change events can be used to keep track of specific values from the config:

```typescript
import shell from '@adobe/exc-app/shell';

constructor() {
  this.state = {environment: null};

  shell.on('change:environment', (env) => {
    this.setState({env});
  });
}

async componentDidMount() {
  const env = await shell.get('environment');
  this.setState({env});
}
```

## Index

### Interfaces

* [ShellApi](../interfaces/shell.shellapi.md)
* [ShellInfo](../interfaces/shell.shellinfo.md)
