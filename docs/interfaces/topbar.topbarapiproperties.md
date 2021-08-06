**[@adobe/exc-app](../README.md)**

> [Globals](../README.md) / [topbar](../modules/topbar.md) / TopbarApiProperties

# Interface: TopbarApiProperties

## Hierarchy

* **TopbarApiProperties**

  ↳ [TopbarApi](topbar.topbarapi.md)

## Index

### Properties

* [customEnvLabel](topbar.topbarapiproperties.md#customenvlabel)
* [solution](topbar.topbarapiproperties.md#solution)
* [workspaces](topbar.topbarapiproperties.md#workspaces)

## Properties

### customEnvLabel

•  **customEnvLabel**: string

Gets or sets a custom environment label in the shell.

***Example:***

```typescript
topbar.customEnvLabel = 'Beta';
```

___

### solution

•  **solution**: [Solution](topbar.solution.md)

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
