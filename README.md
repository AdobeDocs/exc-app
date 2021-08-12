# exc-app

Adobe Experience Cloud gives you everything you need to bring world-class experiences to every
customer. It consists of multiple solutions that power insights, content, engagement, commerce and
optimization.  The unified shell web application at
[https://experience.adobe.com](https://experience.adobe.com) provides a unified user experience for
customers to manage these solutions from a single place.

The solution experiences run within an iframe in the unified shell web application and can interact
with components of the unified shell such as topbar, menus, nps, alerts, etc. These interactions are
made possible through two components: -

1. A module-runtime script that is injected into the product iframe
2. This @adobe/exc-app package that provides an API to interact with the injected module-runtime
script.

- [exc-app](#exc-app)
  - [Getting Started](#getting-started)
  - [Features](#features)
    - [APIs](#apis)
      - [AppApi](#appApi)
      - [CapabilityApi](#capabilityApi)
      - [HelpCenter](#helpcenter)
      - [Metrics](#metrics)
      - [Network](#network)
      - [NPS](#nps)
      - [Page](#page)
      - [Permissions](#permissions)
      - [Pulse](#pulse)
      - [Session](#session)
      - [Settings](#settings)
      - [Shell](#shell)
      - [TopBar](#topbar)
      - [User](#user)
      - [UserProfile](#userprofile)
    - [Events](#events)
      - [Ready](#ready)
      - [Configuration](#configuration)
      - [Receiving Updates](#receiving-updates)
      - [History](#history)
  - [Licensing](#licensing)

## Getting Started

To get started with this integration, below two things need to be done.

1. Include the runtime loader script on the home page
2. Include the [@adobe/exc-app](https://www.npmjs.com/package/@adobe/exc-app) package in your NPM
`package.json` and invoke the init API.

```typescript
import React from 'react';
import ReactDOM from 'react-dom';
import {init} from '@adobe/exc-app';

init(runtime => {
  // Example initialization for a solution that uses React
  ReactDOM.render(<MyProductPage runtime={runtime} />, document.querySelector('#main'));
});
```

## Features

### APIs

#### AppApi
APIs that provide access to certain data types nested inside the app Context.
[learn more](/docs/modules/appapi.md)

#### CapabilityApi
API to request capability icons by id (or secondarily by display name).
[learn more](/docs/modules/capabilityapi.md)

#### HelpCenter

APIs that let solutions interact with the Help Center menu.
[learn more](/docs/modules/helpcenter.md)

#### Metrics

APIs used to log messages, errors, events, metrics and analytics that get pushed to our telemetry
system.
[learn more](/docs/modules/metrics.md)

#### Network

APIs that simplify code to make authenticated network requests for resources, execute GraphQL
queries, etc. and optimize them through efficient batching when appropriate.
[learn more](/docs/modules/network.md)

#### NPS

APIs that let solutions interact with the NPS (Net Promoter Score) widget component, the interface
for recording user experience within a specific solution.
[learn more](/docs/modules/nps.md)


#### Page

APIs that let solutions interact with the main page and personalize it, e.g. setting the title,
favicon, refreshing the solution iframe, etc.
[learn more](/docs/modules/page.md)

#### Permissions

APIs that let solutions query for RBAC permissions of the user.
[learn more](/docs/modules/permissions.md)

#### Pulse

APIs that let solutions interact with Pulse, Adobe's Notification System.
[learn more](/docs/modules/pulse.md)

#### Session

APIs to get, set or invalidate session data.
[learn more](/docs/modules/session.md)

#### Settings

APIs to get or set settings, preferences or configuration data that can be stored and retrieved at
an IMS user and/or an IMS org level. An app in unified shell can consume Settings service.
[learn more](/docs/modules/settings.md)

#### Shell

APIs to request shell-specific information such as environment, imsEnvironment, and shellInfo.
[learn more](/docs/modules/settings.md)

#### TopBar

APIs that let solutions interact with the top bar and personalize it, e.g. configuring the solution
area on the left, setting up workspaces, custom search, etc.
[learn more](/docs/modules/topbar.md)

#### User

APIs to request user-specific information such as IMS organization, IMS profile, access token,
tenant, etc. It also  provides solutions with other capabilities such as notifying the shell that
the session has expired and configuring a logout URL to expire custom sessions.
[learn more](/docs/modules/user.md)

#### UserProfile

APIs that let solutions interact with User Profile menu.
[learn more](/docs/modules/userprofile.md)

### Events

Events are emitted by the module runtime when it receives certain messages from the Unified Shell.

#### Ready

The ready event fires when the initial configuration has been received from the Shell. It would
make sense to wait for this event before rendering the application or setting any workspaces. The
locale will be required to do globalization and we require the workspaces translated prior to
setting them on the Shell, since we don’t (and shouldn’t) have translations for every Solution’s
workspaces.

***Example:***

```typescript
import excApp from '@adobe/exc-app';

function setup() {
  const runtime = excApp();
  runtime.on('ready', ({imsOrg, imsToken, locale}) => {
  this.setState({
      imsOrg,
      imsToken,
      loading: false,
      locale
  });
  });
}
```

***Payload:***

- `activeProductContext`: Active Product Context if one exists 
- `appContainer` 
- `appId`: Id of the current app as defined in the solution config.
- `baseFrameUrl`: Base url for the solution in the iframe.
- `baseUrl`: Base url for the solution in the browser.
- `changedProperties`: Array of properties that have changed.
- `discovery`: Boolean representing if the app uses a discovery url.
- `environment`: Current environment
- `externalQueryParams`: Query Params string.
- `featureFlags`: List of feature flags and values.
- `gainsight`: Gainsight config.
- `gqlEndpoint`: GraphQL endpoint.
- `historyType`: History type as defined in the solution config.
- `hosts`: List of hosts
- `imsClientId`: IMS Client ID
- `imsEnvironment: IMS environment
- `imsInfo`: Object containing imsOrg, imsOrgName, profile, tenant, and imsToken.
- `imsOrg`: Current IMS org
- `imsOrgName: Current IMS org name
- `imsOrgs`: List of IMS Orgs
- `imsProfile`: IMS profile
- `internal`: Boolean
- `ioGatewayUrl`: URL for ioGateway
- `ioRegionSpecificMap`: Map of regions to io endpoints.
- `locale`: Locale
- `metricsAppId`: Metrics app ID
- `metricsConfig`: Metrics configuration.
- `metricsEnv`: Metrics environment
- `preferredLanguages`: List of preferred languages
- `sandbox`: Current sandbox
- `shellHeight`: Shell height in px
- `shellInfo`: Shell info
- `shellSideNavCollapsed`: Boolean representing if the side nav is collapsed
- `shellSideNavPresent`: Boolean representing if the side nav is present
- `shellSideNavWidth`: Shell Side Nav Width in px
- `spaAppId`: spa App Id if the app uses spa-pipeline
- `subOrg`: Current suborg
- `tenant`: Current tenant
- `theme`: Theme
- `xqlGatewayUrl`: xql Gateway Url

#### Configuration

The configuration event fires when any configuration changes from the Shell. This has the same
payload as the ready event.

***Example:***

```typescript
import runtime from '@adobe/exc-app';

function setup() {
  const runtime = excApp();
  runtime.on('configuration', ({imsOrg, imsToken, locale}) => {
    if (imsOrg !== this.state.imsOrg) {
      // Change org
    }
    this.setState({imsOrg, imsToken, locale});
  });
}
```

#### Receiving Updates
After promise fulfillment, in order to get updates on the requested data, the solution must listen for specific change events.

These change events are emitted from the api that the data is requested from. For example, if a user calls `await shell.get('shellInfo');` they must listen for the change event on `shell.on('change:shellInfo')`. If a user calls `await user.get('imsOrg')` they must listen for the change event on `user.on('change:imsOrg')`. Here is a more detailed example of how the promise api and change events can be used to keep track of specific values from the config:

```
constructor() {
  this.state = {org: null, shell: {}};

  user.on('change:imsOrg', (org) => {
    this.setState({org});
  });

  shell.on('change:shellInfo', (shell) => {
    this.setState({shell})
  });
}

async componentDidMount() {
  const [org, shell] = await Promise.all([
    user.get('imsOrg'),
    shell.get('shellInfo'),
  ]);

  this.setState({org, shell});
}
```

#### History

The history event fires when the browser history changes and the frame needs to know about it.

***Example:***

```typescript
import runtime from '@adobe/exc-app';

function setup() {
  const runtime = excApp();
  runtime.on('history', ({type, path}) => {
    const cleanedPath = path[0] === '/' ? path : '/' + path;
    if (type === 'external' && this.history.location.pathname !== cleanedPath) {
      this.history.replace(cleanedPath);
    }
  });
}
```

***Payload:***

- `type`: Internal or external depending on where the event originates from.
- `path`: The new path to update the browser history with.

## Licensing

This project is licensed under the Creative Commons Attribution-NoDerivatives 4.0 International Public License. See [LICENSE](LICENSE) for more information.
