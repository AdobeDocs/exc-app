**[@adobe/exc-app](../README.md)**

> [Globals](../README.md) / [helpCenter](../modules/helpcenter.md) / HelpCenterApiProperties

# Interface: HelpCenterApiProperties

## Hierarchy

* **HelpCenterApiProperties**

  ↳ [HelpCenterApi](helpcenter.helpcenterapi.md)

## Index

### Properties

* [config](helpcenter.helpcenterapiproperties.md#config)

## Properties

### config

•  **config**: [HelpCenterConfig](helpcenter.helpcenterconfig.md)

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
