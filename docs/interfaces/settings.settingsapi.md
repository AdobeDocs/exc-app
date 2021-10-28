**[@adobe/exc-app](../README.md)**

> [Globals](../README.md) / [settings](../modules/settings.md) / SettingsApi

# Interface: SettingsApi

APIs to get or set settings, preferences or configuration data that can be stored and retrieved
at an IMS user and/or an IMS org level. An app in unified shell can consume Settings service.

## Hierarchy

* **SettingsApi**

## Index

### Methods

* [get](settings.settingsapi.md#get)
* [set](settings.settingsapi.md#set)

## Methods

### get

▸ **get**<T\>(`params`: [Parameters](settings.parameters.md)<T\>): Promise<[SettingsResponse](settings.settingsresponse.md)<T\>\>

Gets settings based on the specified parameters such as groupId
and settings - keys with default values to fallback.

#### Type parameters:

Name | Type |
------ | ------ |
`T` | [Settings](settings.settings-1.md) |

#### Parameters:

Name | Type | Description |
------ | ------ | ------ |
`params` | [Parameters](settings.parameters.md)<T\> | Parameters used to identify settings to retrieve. |

**Returns:** Promise<[SettingsResponse](settings.settingsresponse.md)<T\>\>

A promise for the specified settings.

___

### set

▸ **set**<T\>(`params`: [Parameters](settings.parameters.md)<T\>): Promise<[SettingsResponse](settings.settingsresponse.md)<T\>\>

Creates or updates settings based on the specified parameters such as groupId and settings
key-value pairs.

#### Type parameters:

Name | Type |
------ | ------ |
`T` | [Settings](settings.settings-1.md) |

#### Parameters:

Name | Type | Description |
------ | ------ | ------ |
`params` | [Parameters](settings.parameters.md)<T\> | Parameters to identify the settings to create or update. |

**Returns:** Promise<[SettingsResponse](settings.settingsresponse.md)<T\>\>

A promise for the operation response.
