**[@adobe/exc-app](../README.md)**

> [Globals](../README.md) / settings

# Module: settings

APIs to get or set settings, preferences or configuration data that can be stored and retrieved
at an IMS user and/or an IMS org level. An app in unified shell can consume Settings service.

To consume this API, add the following import to your code.

```typescript
import settings from '@adobe/exc-app/settings';
```

The default export is an object of type [SettingsApi](../interfaces/_settings_.settingsapi.md)

API reference: [scroll down](#index)

### Sample code

```typescript
import settings, {SettingsLevel} from '@adobe/exc-app/settings';

async function updateSettings(type: string, value: number) {
  const data = await settings.get({
    groupId: 'test-groupId',
    level: SettingsLevel.USER,
    settings: {key1: null}
  });
  data = data || {};
  data[type] = value;
  await settings.set({
    groupId: 'test-groupId',
    level: SettingsLevel.USER,
    settings: {key1: data}
  });
}
```

### SettingsLevel

Can be optionally specified to define the level at which settings are saved.

* `SettingsLevel.USER` - use this level when you want to get/set settings per user.
* `SettingsLevel.USERORG` - should be used when settings are for user + org combination.
* `SettingsLevel.ORG` - use this level when you want to get/set settings per org.

By default settings are saved at level `SettingsLevel.USERORG`. You can optionally override this
in the get/set API calls using the `level` parameter.

### Groups

Apps can group their settings into different groups by different group IDs and keep multiple
settings in different groups. Apps are free to define their own groups for a particular selected
settings level.

You can specify this in the get/set API calls using the `groupId` parameter.

### Sharing settings

Set settingsAppId in the solution specific route configuration in order to share settings with
other applications.

## Index

### Interfaces

* [Parameters](../interfaces/settings.parameters.md)
* [Settings](../interfaces/settings.settings-1.md)
* [SettingsApi](../interfaces/settings.settingsapi.md)
* [SettingsResponse](../interfaces/settings.settingsresponse.md)
