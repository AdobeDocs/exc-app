**[@adobe/exc-app](../README.md)**

> [Globals](../README.md) / pulse

# Module: pulse

APIs that let solutions interact with Pulse, Adobe's Notification System.

***Import:***

```typescript
import pulse from '@adobe/exc-app/pulse';
```

***Default export:***

[PulseApi](../interfaces/pulse.pulseapi.md#interface-pulserapi)

***Usage:***

```typescript
import pulse, {NotificationType} from '@adobe/exc-app/pulse';

pulse.send([{
  groupIds: [],
  messageType: NotificationType.UPDATES_ON_SUBSCRIBED_OBJECT,
  metadata: {priority: 'low'},
  sendToOrg: false,
  templateParams: {message: 'System shared Asset shared'},
  userIds: []
}]);
```

API for sending pulse notifications.

## Index

### Interfaces

* [PulseApi](../interfaces/pulse.pulseapi.md)
* [PulseButtonConfig](../interfaces/pulse.pulsebuttonconfig.md)
* [PulseNotification](../interfaces/pulse.pulsenotification.md)
* [PulseResponse](../interfaces/pulse.pulseresponse.md)
