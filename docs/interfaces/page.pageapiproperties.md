**[@adobe/exc-app](../README.md)**

> [Globals](../README.md) / [page](../modules/page.md) / PageApiProperties

# Interface: PageApiProperties

Subset of page-level APIs available to solutions that are settable attributes.

## Hierarchy

* **PageApiProperties**

  ↳ [PageApi](page.pageapi.md)

## Index

### Properties

* [appContainer](page.pageapiproperties.md#appcontainer)
* [favicon](page.pageapiproperties.md#favicon)
* [modal](page.pageapiproperties.md#modal)
* [modalAutoDetect](page.pageapiproperties.md#modalautodetect)
* [preventDefaultCombos](page.pageapiproperties.md#preventdefaultcombos)
* [spinner](page.pageapiproperties.md#spinner)
* [title](page.pageapiproperties.md#title)
* [unloadPromptMessage](page.pageapiproperties.md#unloadpromptmessage)

## Properties

### appContainer

•  **appContainer**: string

Configuration for specifying which element should have the left margin and top margin added to it when
fullscreen overlay or modal needs to be displayed. Left margin will only be added if there is a side nav.
This should be a string with an element selector.

***Example:***

```typescript
page.appContainer = '#example'
```

___

### favicon

•  **favicon**: string

Gets or set the favicon for the page. If this isn't set, then the default experience cloud
favicon will be used.

***Example:***

```typescript
page.favicon = "https://img.icons8.com/color/48/000000/thumb-up.png";
```

___

### modal

•  **modal**: boolean

Configuration to show/hide a modal with fullscreen overlay. Defaults to false.

***Example:***

```typescript
page.modal = true;
```

___

### modalAutoDetect

•  **modalAutoDetect**: boolean

Toggle for whether or not runtime should observe DOM changes and check the changes against
modal query selectors to automatically set modal = true. If you use this option consider adding
selectors with setModalQuerySelectors.

***Example:***

```typescript
page.modalAutoDetect = true;
```

___

### preventDefaultCombos

•  **preventDefaultCombos**: { altKey?: undefined \| false \| true ; ctrlKey?: undefined \| false \| true ; key: string ; metaKey?: undefined \| false \| true ; shiftKey?: undefined \| false \| true  }[]

An array of key combinations for the shell to prevent default browser behavior on in cases
where an application performs some other action.

***Example:***

```typescript
page.preventDefaultCombos = [
  {
    ctrlKey: true,
    key: 's'
  }
];
```

___

### spinner

•  **spinner**: boolean

Gets or sets a value indicating whether or not to show a spinner on the page. This
configuration value is NOT used for the initial loading spinner (see Route Configuration
hideInitialSpinner for that), but can be used to dismiss it if the spinner needs to be
dismissed before a solution invokes runtime.done().

***Example:***

```typescript
page.spinner = true;
```

___

### title

•  **title**: string

Gets or sets the title of the page.

***Example:***

```typescript
page.title = 'Adobe Experience Cloud';
```

___

### unloadPromptMessage

•  **unloadPromptMessage**: string

Sets a message to be displayed if the user is prompted before navigating away from the page.
This will only be effective if page.blockNavigation is being used. Prompt messages should be
localized based on the current locale of the user before being set. The default value is 'Are you sure?'.

***Example:***

```typescript
page.unloadPromptMessage = 'Are you sure you want to leave?';
```
