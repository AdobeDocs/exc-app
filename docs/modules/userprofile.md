**[@adobe/exc-app](../README.md)**

> [Globals](../README.md) / userProfile

# Module: userProfile

APIs that let solutions interact with User Profile menu.

***Import:***

```typescript
import userProfile from '@adobe/exc-app/userProfile';
```

***Default export:***

[UserProfileApi](../interfaces/userprofile.userprofileapi.md#interface-userprofileapi)

***Usage:***

```typescript
import userProfile from '@adobe/exc-app/userProfile';

userProfile.setButtons([{
  callback: () => {},
  id: 'button',
  label: 'Button'
}]);
```

This configuration is a method only for solutions that need to manage alternative User Profile flows not covered by the Shell.

## Index

### Interfaces

* [Button](../interfaces/userprofile.button.md)
* [UserProfileApi](../interfaces/userprofile.userprofileapi.md)

### Type aliases

* [ButtonArray](userprofile.md#buttonarray)

## Type aliases

### ButtonArray

Ƭ  **ButtonArray**: [] \| [[Button](../interfaces/userprofile.button.md)] \| [[Button](../interfaces/userprofile.button.md), [Button](../interfaces/userprofile.button.md)] \| [[Button](../interfaces/userprofile.button.md), [Button](../interfaces/userprofile.button.md), [Button](../interfaces/userprofile.button.md)]

A maximum of 3 buttons can be supplied.
