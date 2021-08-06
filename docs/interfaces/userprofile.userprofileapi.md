**[@adobe/exc-app](../README.md)**

> [Globals](../README.md) / [userProfile](../modules/userprofile.md) / UserProfileApi

# Interface: UserProfileApi

Defines the user profile api.

## Hierarchy

* **UserProfileApi**

## Index

### Methods

* [setButtons](userprofile.userprofileapi.md#setbuttons)

## Methods

### setButtons

▸ **setButtons**(`buttons`: [ButtonArray](../modules/userprofile.md#buttonarray) \| null): void

Adds custom button(s) to the profile dropdown and enacts a callback onclick.
Custom user profile buttons may be reset by entering a null parameter.
A maximum of 3 custom buttons will be displayed in the User Profile popover.

```typescript
userProfile.setButtons([
  {
    callback: () => {},
    label: 'Alpha',
    id: 'alpha'
  },
  {
    callback: () => {},
    label: 'View My Profile',
    id: 'viewprofile'
  }
]);
```

#### Parameters:

Name | Type |
------ | ------ |
`buttons` | [ButtonArray](../modules/userprofile.md#buttonarray) \| null |

**Returns:** void
