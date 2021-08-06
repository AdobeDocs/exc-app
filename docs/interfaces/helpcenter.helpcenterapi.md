**[@adobe/exc-app](../README.md)**

> [Globals](../README.md) / [helpCenter](../modules/helpcenter.md) / HelpCenterApi

# Interface: HelpCenterApi

Defines helpCenter-level APIs available to solutions.

## Hierarchy

* [HelpCenterApiProperties](helpcenter.helpcenterapiproperties.md)

  ↳ **HelpCenterApi**

## Index

### Properties

* [config](helpcenter.helpcenterapi.md#config)

### Methods

* [close](helpcenter.helpcenterapi.md#close)
* [open](helpcenter.helpcenterapi.md#open)
* [setButton](helpcenter.helpcenterapi.md#setbutton)
* [setButtons](helpcenter.helpcenterapi.md#setbuttons)

## Properties

### config

•  **config**: [HelpCenterConfig](helpcenter.helpcenterconfig.md)

*Inherited from [HelpCenterApiProperties](helpcenter.helpcenterapiproperties.md).[config](helpcenter.helpcenterapiproperties.md#config)*

Gets or sets the configuration for Help Center.

```typescript
helpCenter.config = {
  featured: [
    {
      href: 'https://helpx.adobe.com/support/experience-cloud.html',
      label: 'Adobe Experience Cloud Learn & Support',
      path: '/:orgId?/home'
    },
    {
      href: 'https://helpx.adobe.com/support/target.html',
      label: 'Adobe Target'
    }
  ],
  recommendations: {
    enabled: true,
    terms: [
      {
        path: '/:orgId?/analytics/home/(.*)?',
        term: 'get started'
      },
      {
        path: '/:orgId?/analytics/create',
        term: 'create new'
      }
    ]
  },
  resources: [
    {
      href: 'https://marketing.adobe.com/resources/help/en_US/home/index.html',
      label: 'Help Home'
    }
  ]
};
```

## Methods

### close

▸ **close**(): void

Method to close the help center from within the iframe.

```typescript
helpCenter.close();
```

**Returns:** void

___

### open

▸ **open**(`config?`: [HelpCenterOpenConfig](helpcenter.helpcenteropenconfig.md)): void

Method to open the help center from within the iframe.

```typescript
helpCenter.open({
  config: {
    subject: 'Analytics'
    type: 'CONTEXTUAL_FEEDBACK_SUBMISSION'
  },
  selectedTab: 'feedback'
});
```

#### Parameters:

Name | Type |
------ | ------ |
`config?` | [HelpCenterOpenConfig](helpcenter.helpcenteropenconfig.md) |

**Returns:** void

___

### setButton

▸ **setButton**(`config`: [HelpCenterButtonConfig](helpcenter.helpcenterbuttonconfig.md) \| [HelpCenterButtonConfig](helpcenter.helpcenterbuttonconfig.md)[] \| null): void

Adds a custom button to the help center and enacts a callback onclick.
The button will be present under the support tab in help center.
The help center button may be reset by entering a null parameter.

```typescript
helpCenter.setButton({
  callback: () => {},
  label: 'Create Support Ticket'
});
```

#### Parameters:

Name | Type |
------ | ------ |
`config` | [HelpCenterButtonConfig](helpcenter.helpcenterbuttonconfig.md) \| [HelpCenterButtonConfig](helpcenter.helpcenterbuttonconfig.md)[] \| null |

**Returns:** void

___

### setButtons

▸ **setButtons**(`buttons`: [HelpCenterButtonConfig](helpcenter.helpcenterbuttonconfig.md)[] \| null): void

Adds 1-many custom buttons to the help center and enacts a callback onclick.
Depending on the scope (helpCenter or helpCenterResource), the buttons will
be present under the support tab (helpCenter) or at the button of the
resources section on the main tab (helpCenterResource) in help center.
The help center button may be reset by entering a null parameter.

```typescript
helpCenter.setButtons([{
  callback: () => {},
  id: 'support',
  label: 'Create Support Ticket',
  scope: 'helpCenter'
}]);
```

#### Parameters:

Name | Type |
------ | ------ |
`buttons` | [HelpCenterButtonConfig](helpcenter.helpcenterbuttonconfig.md)[] \| null |

**Returns:** void
