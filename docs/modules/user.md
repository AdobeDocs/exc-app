**[@adobe/exc-app](../README.md)**

> [Globals](../README.md) / user

# Module: user

API to request user-specific information such as IMS organization, IMS profile, access token,
tenant, etc. It also  provides solutions with other capabilities such as notifying the shell that
the session has expired and configuring a logout URL to expire custom sessions.

***Import:***

```typescript
import user from '@adobe/exc-app/user';
```

***Default export:***

[UserApi](../interfaces/user.userapi.md#interface-userapi)

***Usage:***

Below is an example of how to get various attributes associated to the user:

```typescript
import user from '@adobe/exc-app/user';

const [orgInfo, org, name, orgs, token, profile, locale, languages, subOrg, tenant, theme] = await Promise.all([
  user.get('imsInfo'),
  user.get('imsOrg'),
  user.get('imsOrgName'),
  user.get('imsOrgs'),
  user.get('imsToken'),
  user.get('imsProfile'),
  user.get('locale'),
  user.get('preferredLanguages'),
  user.get('subOrg'),
  user.get('tenant'),
  user.get('theme')
]);
```

### Receiving updates

You can also listen for updates on the requested data by listening to specific change events.

These change events are emitted from the api that the data is requested from. For example, if a
user calls `await user.get('locale');` they must listen for the change event on
`user.on('change:locale')`. If a user calls `await user.get('imsOrg')` they must listen for the
change event on `user.on('change:imsOrg')`. Here is a more detailed example of how the promise
api and change events can be used to keep track of specific values from the config:

```typescript
import user from '@adobe/exc-app/user';

constructor() {
  this.state = {org: null, shell: {}};

  user.on('change:imsOrg', (org) => {
    this.setState({org});
  });
}

async componentDidMount() {
  const org = await user.get('imsOrg');
  this.setState({org});
}
```

imsInfo is a special case. When listening for updates on imsInfo, the callback will receive
two arguments. The first is the entire imsInfo object. The second is an object containing only
the values that have changed (for example, an org change between an individual account and a
type2e account will cause the imsProfile to change, while an org change within the same account will not).

```typescript
 user.on('change:imsInfo', (info, changed) => {
    if ('imsProfile' in changed) {
      // load information for new account
    }

    this.setState({...info});
  });
```

## Index

### Interfaces

* [IMS](../interfaces/user.ims.md)
* [IMSInfo](../interfaces/user.imsinfo.md)
* [Sandbox](../interfaces/user.sandbox.md)
* [UserApi](../interfaces/user.userapi.md)
* [UserInfo](../interfaces/user.userinfo.md)

### Type aliases

* [LogoutUrl](user.md#logouturl)

## Type aliases

### LogoutUrl

Ƭ  **LogoutUrl**: string \| { distinctDomain?: undefined \| false \| true ; url: string  }

Logout URL can either be a string or an object. The object includes the URL
to be called on logout and whether this URL should be the only version of the
host in the logout list.
