**[@adobe/exc-app](../README.md)**

> [Globals](../README.md) / [page](../modules/page.md) / PageApi

# Interface: PageApi

Defines page-level APIs available to solutions.

## Hierarchy

* [PageApiProperties](page.pageapiproperties.md)

  ↳ **PageApi**

## Index

### Properties

* [appContainer](page.pageapi.md#appcontainer)
* [favicon](page.pageapi.md#favicon)
* [modal](page.pageapi.md#modal)
* [modalAutoDetect](page.pageapi.md#modalautodetect)
* [preventDefaultCombos](page.pageapi.md#preventdefaultcombos)
* [spinner](page.pageapi.md#spinner)
* [title](page.pageapi.md#title)
* [unloadPromptMessage](page.pageapi.md#unloadpromptmessage)

### Methods

* [afterPrintHandler](page.pageapi.md#afterprinthandler)
* [beforePrintHandler](page.pageapi.md#beforeprinthandler)
* [blockNavigation](page.pageapi.md#blocknavigation)
* [clipboardWrite](page.pageapi.md#clipboardwrite)
* [done](page.pageapi.md#done)
* [generateShellUrl](page.pageapi.md#generateshellurl)
* [getModalQuerySelectors](page.pageapi.md#getmodalqueryselectors)
* [iframeReload](page.pageapi.md#iframereload)
* [notFound](page.pageapi.md#notfound)
* [openInNewTab](page.pageapi.md#openinnewtab)
* [print](page.pageapi.md#print)
* [setModalQuerySelectors](page.pageapi.md#setmodalqueryselectors)
* [shellRedirect](page.pageapi.md#shellredirect)

## Properties

### appContainer

•  **appContainer**: string

*Inherited from [PageApiProperties](page.pageapiproperties.md).[appContainer](page.pageapiproperties.md#appcontainer)*

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

*Inherited from [PageApiProperties](page.pageapiproperties.md).[favicon](page.pageapiproperties.md#favicon)*

Gets or set the favicon for the page. If this isn't set, then the default experience cloud
favicon will be used.

***Example:***

```typescript
page.favicon = "https://img.icons8.com/color/48/000000/thumb-up.png";
```

___

### modal

•  **modal**: boolean

*Inherited from [PageApiProperties](page.pageapiproperties.md).[modal](page.pageapiproperties.md#modal)*

Configuration to show/hide a modal with fullscreen overlay. Defaults to false.

***Example:***

```typescript
page.modal = true;
```

___

### modalAutoDetect

•  **modalAutoDetect**: boolean

*Inherited from [PageApiProperties](page.pageapiproperties.md).[modalAutoDetect](page.pageapiproperties.md#modalautodetect)*

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

*Inherited from [PageApiProperties](page.pageapiproperties.md).[preventDefaultCombos](page.pageapiproperties.md#preventdefaultcombos)*

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

*Inherited from [PageApiProperties](page.pageapiproperties.md).[spinner](page.pageapiproperties.md#spinner)*

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

*Inherited from [PageApiProperties](page.pageapiproperties.md).[title](page.pageapiproperties.md#title)*

Gets or sets the title of the page.

***Example:***

```typescript
page.title = 'Adobe Experience Cloud';
```

___

### unloadPromptMessage

•  **unloadPromptMessage**: string

*Inherited from [PageApiProperties](page.pageapiproperties.md).[unloadPromptMessage](page.pageapiproperties.md#unloadpromptmessage)*

Sets a message to be displayed if the user is prompted before navigating away from the page.
This will only be effective if page.blockNavigation is being used. Prompt messages should be
localized based on the current locale of the user before being set. The default value is 'Are you sure?'.

***Example:***

```typescript
page.unloadPromptMessage = 'Are you sure you want to leave?';
```

## Methods

### afterPrintHandler

▸ **afterPrintHandler**(`callback`: [Callback](page.callback.md)): void

A function that listens and handles the afterPrint event.

```typescript
***Example:***
page.afterPrintHandler = function () {
  // Revert temporary CSS changes
};
````

#### Parameters:

Name | Type | Description |
------ | ------ | ------ |
`callback` | [Callback](page.callback.md) | The function that results in printing.  |

**Returns:** void

___

### beforePrintHandler

▸ **beforePrintHandler**(`callback`: [Callback](page.callback.md)): void

A function that listens and handles the beforePrint event.

```typescript
***Example:***
page.beforePrintHandler = function () {
  // Temporary CSS changes, like unsetting height
};
````

#### Parameters:

Name | Type | Description |
------ | ------ | ------ |
`callback` | [Callback](page.callback.md) | The function that results in printing.  |

**Returns:** void

___

### blockNavigation

▸ **blockNavigation**(`enabled`: boolean, `options?`: [BlockNavigationOptions](page.blocknavigationoptions.md)): void

Sometimes applications will need to block navigation away from the current page. The most common use case
for this is when a user has unsaved changes that would be lost on navigation.

There are 3 types of navigation in unified shell that must be accounted for:
1. User attempts to navigate in a way that will cause the browser to reload. This includes page refreshes, manual URL changes, and solution switcher clicks to a non-unified shell application.
2. User attempts to navigate to another page hosted on unified shell via the shell. This includes workspace clicks, org changes, and solution switches to a unified shell application. Because this is only a hash history change, it does not cause a full browser reload.
3. User attempts to navigate to another page in the current application via a link in the iframe.

In order to prevent the first and second types of navigation, unified shell offers a `blockNavigation` function. To turn on navigation blocking, the application should set:

***Example:***

```typescript
page.blockNavigation(true);
```
When this function is called with `true`, Unified Shell will set a `beforeUnload` handler on the page. This will block the first type of navigation. Unified Shell will also use `history.block` to block hash navigations such as org switches and workspace changes.
To handle the third type of navigation, applications must block the location change from within the iframe before it propogates to the shell. This is because unified shell won't know about the iframe navigation until after it happens.
To solve for this, solutions should `history.block` from within the iframe as well. It is important to note that only `push` location changes should be blocked. If the solution blocks all location changes, the navigation blocking prompt will be shown to the user multiple times.
When navigation blocking is no longer needed the application should set `runtime.blockNavigation(false)`.

In special cases, a solution may want to allow workspace changes but block any other type of navigation. To enable this, the option `onOrgChangeOnly` should be passed in.

***Example:***

```
runtime.blockNavigation(true, {onOrgChangeOnly: true});
```

Please note that navigation blocking is currently only supported for tenanted solutions. If you would like to block navigation from a tenantless solution please contact a unified shell team member to discuss your use case.

#### Parameters:

Name | Type |
------ | ------ |
`enabled` | boolean |
`options?` | [BlockNavigationOptions](page.blocknavigationoptions.md) |

**Returns:** void

___

### clipboardWrite

▸ **clipboardWrite**(`msg`: string): void

Browsers do not currently allow pages within the iframe to write data to the user's clipboard.
Utilizing this method, we are able to check that the user has granted permission to write to
their clipboard and then do so.

**Example:**

```typescript
page.clipboardWrite('Message to write to the clipboard');
```

#### Parameters:

Name | Type | Description |
------ | ------ | ------ |
`msg` | string | The string to write to the clipboard.  |

**Returns:** void

___

### done

▸ **done**(): void

Tells the Shell that the Solution has loaded and is ready to be used by a user and dismisses
the initial loading spinner.

At the earliest, done should be called after Ready event was fired to ensure accurate reporting.

One of the main objectives of using done is to measure UX performance, it should be called after
all network activity is completed and the app is interactive - Ready for users to do their work.

***Example:***

```typescript
page.done();
```

**Returns:** void

___

### generateShellUrl

▸ **generateShellUrl**(`location`: [LocationLike](../modules/page.md#locationlike), `newApp?`: undefined \| false \| true): string

Method to take a relative path or full iframe URL and generate a unified shell url.

***Example:***

```typescript
// returns `https://experience.adobe.com/#/@tenant/solution/abc`
page.generateShellUrl({path: '/abc'});

// returns `https://experience.adobe.com/#/@tenant/sname:prod/solution/abc`
page.generateShellUrl({path: '/abc', sandbox: 'prod'});

// returns `https://experience.adobe.com/#/@tenant/solution/abc`
page.generateShellUrl({href: 'https://example.com/abc'});
```

#### Parameters:

Name | Type | Description |
------ | ------ | ------ |
`location` | [LocationLike](../modules/page.md#locationlike) | Object with either a path and optional sandbox or href key and corresponding value from which to generate the shell URL. |
`newApp?` | undefined \| false \| true | When true generates a new url with the given location without hash values or pathname resolutions specific to the current app. |

**Returns:** string

The shell URL for the specified view of the solution.

___

### getModalQuerySelectors

▸ **getModalQuerySelectors**(): Array<string\>

Get the list of selectors presently being used by modalAutoDetect.

***Example:***

```typescript
page.getModalQuerySelectors({path: '/abc'});
```

**Returns:** Array<string\>

The list of selectors presently being used by modalAutoDetect.

___

### iframeReload

▸ **iframeReload**(`cacheBust?`: undefined \| false \| true): void

Triggers the reload of the solution iframe. Calling this function will regenerate the iframe
source, triggering the discovery URL flow if configured.

***Example:***

```typescript
page.iframeReload();
```

#### Parameters:

Name | Type | Description |
------ | ------ | ------ |
`cacheBust?` | undefined \| false \| true | Whether the reload should include a unique query param on the iframe URL to cache bust the page. This defaults to false for SPA pipeline apps, true to other apps for backwards compatibility purposes.  |

**Returns:** void

___

### notFound

▸ **notFound**(): void

Replaces the application iframe with the not found page.

***Example:***

```typescript
page.notFound();
```

**Returns:** void

___

### openInNewTab

▸ **openInNewTab**(`path`: string, `newApp?`: undefined \| false \| true): void

Opens the specified URL in the shell in a new tab. This is useful in scenarios where an element
won't be an anchor or link and solution needs to open the URL.

***Example:***

```typescript
page.openInNewTab('/path');
```

#### Parameters:

Name | Type | Description |
------ | ------ | ------ |
`path` | string | The relative path within the solution. |
`newApp?` | undefined \| false \| true | When true generates a new url with the given location without hash values or pathname resolutions specific to the current app.  |

**Returns:** void

___

### print

▸ **print**(`callback`: [Callback](page.callback.md)): void

A function to control printing. The callback function should call `window.print()`
at some point. It's important that the callback not be an arrow function if you
want the `window` object to be the iframe contents. Feel free to adjust your
CSS or UI before `window.print()` and reverse those changes afterwards.

```typescript
***Example:***
page.print = function () {
  window.print();
};
````

#### Parameters:

Name | Type | Description |
------ | ------ | ------ |
`callback` | [Callback](page.callback.md) | The function that results in printing.  |

**Returns:** void

___

### setModalQuerySelectors

▸ **setModalQuerySelectors**(`selectors`: Array<string\>): void

Set the list of selectors presently being used by modalAutoDetect. If set to an empty
array, the default selectors used by runtime will be used instead. To stop observing changes
unset modalAutoDetect. Setting additonal selectors replaces the currently set selectors, use
page.getModalQuerySelectors and append new selectors to the returned list before resetting
to modify the existing list of selectors.

***Example:***

```typescript
page.setModalQuerySelectors(['.someSpecialCaseModal', '.yourNormalModal']);
```

#### Parameters:

Name | Type | Description |
------ | ------ | ------ |
`selectors` | Array<string\> | The list of selectors for modalAutoDetect to use.  |

**Returns:** void

___

### shellRedirect

▸ **shellRedirect**(`path`: string, `options?`: [ShellRedirectOptions](page.shellredirectoptions.md)): void

Redirects to another unified shell solution. Path should be the complete relative path of a
valid unified shell solution url (i.e. if shellRedirect is called from /target to /analytics,
the path paremeter would need to start with /analytics). Query and hash are optional.

***Example:***

```typescript
page.shellRedirect('/path?a=b#workspace');
```

#### Parameters:

Name | Type | Description |
------ | ------ | ------ |
`path` | string | Path including search and hash to a unified shell solution. |
`options?` | [ShellRedirectOptions](page.shellredirectoptions.md) | Options for redirect. Options include discovery which determines if the new location requires a discovery call and replace which determines if the history action should be a replace or push.  |

**Returns:** void
