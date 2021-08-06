**[@adobe/exc-app](../README.md)**

> [Globals](../README.md) / [topbar](../modules/topbar.md) / TopbarApi

# Interface: TopbarApi

Defines page-level APIs available to solutions.

## Hierarchy

* [TopbarApiProperties](topbar.topbarapiproperties.md)

  ↳ **TopbarApi**

## Index

### Properties

* [customEnvLabel](topbar.topbarapi.md#customenvlabel)
* [solution](topbar.topbarapi.md#solution)
* [workspaces](topbar.topbarapi.md#workspaces)

### Methods

* [onHeroClick](topbar.topbarapi.md#onheroclick)
* [setCustomSearch](topbar.topbarapi.md#setcustomsearch)
* [setFeedbackButton](topbar.topbarapi.md#setfeedbackbutton)

## Properties

### customEnvLabel

•  **customEnvLabel**: string

*Inherited from [TopbarApiProperties](topbar.topbarapiproperties.md).[customEnvLabel](topbar.topbarapiproperties.md#customenvlabel)*

Gets or sets a custom environment label in the shell.

***Example:***

```typescript
topbar.customEnvLabel = 'Beta';
```

___

### solution

•  **solution**: [Solution](topbar.solution.md)

*Inherited from [TopbarApiProperties](topbar.topbarapiproperties.md).[solution](topbar.topbarapiproperties.md#solution)*

Configuration for solution name and hero. All values aside from
path can only be used by third party applications. All other solutions will use
their default product set branding as of the 2020 branding changes.

***Example:***

```typescript
topbar.solution = {
  icon: 'AdobeExperienceCloud',
  path: '/alternatepath/for/heroclick',
  shortTitle: 'AEC',
  title: 'Adobe Experience Cloud22'
};
```

___

### workspaces

•  **workspaces**: WorkspaceMenu[]

*Inherited from [TopbarApiProperties](topbar.topbarapiproperties.md).[workspaces](topbar.topbarapiproperties.md#workspaces)*

Configuration for the Shell workspaces. Workspace names should be unique, and should be
localized using the unified shell locale prior to setting runtime.workspaces.

```typescript
topbar.workspaces = [
  {name: 'Home', url: '/'},
  {name: 'ABC', url: '/abc'},
  {name: 'DEF', url: '/def'}
];
```

Unified shell also supports workspace flyout menus, where clicking on a workspace displays a
dropdown menu. The top-level workspace is present in the dropdown menu as the first menu item.
Menus may be nested multiple times, and used in combination with normal workspaces. By default,
parent menu items will be automatically added to the sub-menu due to how the user interaction
works. To prevent this functionality, simply remove the url property on the parent item and it
will not be injected into the sub-menu.

```typescript
topbar.workspaces = [
  {name: 'Home', url: '/'},
  {name: 'ABC', url: '/abc'},
  {
    name: 'DEF',
    url: '/def',
    menu: [
      {
        name: 'GHI',
        url: '/def/ghi',
        menu: [
          {name: 'JKL', url: '/def/ghi/jkl'}
        ]
      }
    ]
  }
];
```

## Methods

### onHeroClick

▸ **onHeroClick**(`callback`: [Callback](topbar.callback.md)): void

Registers a callback to execute when the hero (solution) icon in the upper lefthand corner of
the Shell is clicked.

#### Parameters:

Name | Type | Description |
------ | ------ | ------ |
`callback` | [Callback](topbar.callback.md) | The callback to execute.  |

**Returns:** void

___

### setCustomSearch

▸ **setCustomSearch**(`config`: [CustomSearchConfig](topbar.customsearchconfig.md) \| null): void

Determines whether or not to enable the custom search property and enacts a callback
when the custom search icon is clicked.

#### Parameters:

Name | Type |
------ | ------ |
`config` | [CustomSearchConfig](topbar.customsearchconfig.md) \| null |

**Returns:** void

___

### setFeedbackButton

▸ **setFeedbackButton**(`config`: [CustomFeedbackConfig](topbar.customfeedbackconfig.md) \| [HelpCenterFeedbackConfig](topbar.helpcenterfeedbackconfig.md) \| [ExternalFeedbackConfig](topbar.externalfeedbackconfig.md) \| null): void

Determines whether or not to enable a feedback button.

#### Parameters:

Name | Type |
------ | ------ |
`config` | [CustomFeedbackConfig](topbar.customfeedbackconfig.md) \| [HelpCenterFeedbackConfig](topbar.helpcenterfeedbackconfig.md) \| [ExternalFeedbackConfig](topbar.externalfeedbackconfig.md) \| null |

**Returns:** void
