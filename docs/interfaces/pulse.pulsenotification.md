**[@adobe/exc-app](../README.md)**

> [Globals](../README.md) / [pulse](../modules/pulse.md) / PulseNotification

# Interface: PulseNotification

## Hierarchy

* **PulseNotification**

## Index

### Properties

* [groupIds](pulse.pulsenotification.md#groupids)
* [messageType](pulse.pulsenotification.md#messagetype)
* [metadata](pulse.pulsenotification.md#metadata)
* [sendToOrg](pulse.pulsenotification.md#sendtoorg)
* [templateParams](pulse.pulsenotification.md#templateparams)
* [userIds](pulse.pulsenotification.md#userids)

## Properties

### groupIds

• `Optional` **groupIds**: string[]

List of group ids to receive notification.

___

### messageType

•  **messageType**: NotificationType

Type of Notification to be sent.

___

### metadata

• `Optional` **metadata**: Record<string, string\>

A map of key value pairs which can be provided by publisher of notification for the consumer.

___

### sendToOrg

• `Optional` **sendToOrg**: undefined \| false \| true

Specifies whether to send notifications to the complete IMS org.

___

### templateParams

•  **templateParams**: Record<string, any\>

Templated parameters.

___

### userIds

• `Optional` **userIds**: string[]

List of IMS user ids of the users to receive notification.
A maximum of 100 user-ids are supported at a time.
