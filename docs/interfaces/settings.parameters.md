**[@adobe/exc-app](../README.md)**

> [Globals](../README.md) / [settings](../modules/settings.md) / Parameters

# Interface: Parameters<T\>

The input parameters for the settings API.

## Type parameters

Name | Type |
------ | ------ |
`T` | [Settings](settings.settings-1.md) |

## Hierarchy

* **Parameters**

## Index

### Properties

* [groupId](settings.parameters.md#groupid)
* [level](settings.parameters.md#level)
* [settings](settings.parameters.md#settings)

## Properties

### groupId

•  **groupId**: string

A unique identifier.

___

### level

• `Optional` **level**: SettingsLevel

The type of store to get/set the settings from/to. Defaults to `SettingsLevel.USERORG`.

___

### settings

•  **settings**: T

A map of the settings key-value pairs. In case of `set` API, the value is saved and for the
`get` API, the value is the fallback in case the key isn't present in the settings store.
