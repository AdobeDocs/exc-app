**[@adobe/exc-app](../README.md)**

> [Globals](../README.md) / [pulse](../modules/pulse.md) / PulseApi

# Interface: PulseApi

## Hierarchy

* **PulseApi**

## Index

### Methods

* [send](pulse.pulseapi.md#send)
* [setButton](pulse.pulseapi.md#setbutton)
* [setCount](pulse.pulseapi.md#setcount)

## Methods

### send

▸ **send**(`notifications`: [PulseNotification](pulse.pulsenotification.md)[]): Promise<[PulseResponse](pulse.pulseresponse.md)\>

Method to send a pulse notification.

#### Parameters:

Name | Type |
------ | ------ |
`notifications` | [PulseNotification](pulse.pulsenotification.md)[] |

**Returns:** Promise<[PulseResponse](pulse.pulseresponse.md)\>

___

### setButton

▸ **setButton**(`buttonConfig`: [PulseButtonConfig](pulse.pulsebuttonconfig.md)): void

Adds an additional custom button to the bottom of the Pulse container.
Will fire the attached callback when a user presses the button.

#### Parameters:

Name | Type | Description |
------ | ------ | ------ |
`buttonConfig` | [PulseButtonConfig](pulse.pulsebuttonconfig.md) | The button configuration  |

**Returns:** void

___

### setCount

▸ **setCount**(`count`: number): void

Adds additional values to the notification.
If Pulse has 3 internally and this is set to 2, the UI will show 5.

#### Parameters:

Name | Type | Description |
------ | ------ | ------ |
`count` | number | Additional values to add to the pulse notification.  |

**Returns:** void
