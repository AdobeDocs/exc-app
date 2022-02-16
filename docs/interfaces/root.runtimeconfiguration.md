**[@adobe/exc-app](../README.md)**

> [Globals](../README.md) / [root](../modules/root.md) / RuntimeConfiguration

# Interface: RuntimeConfiguration

External Runtime Configuration Interface

## Hierarchy

* **RuntimeConfiguration**

## Index

### Properties

* [analytics](root.runtimeconfiguration.md#analytics)
* [apiGatewayUrl](root.runtimeconfiguration.md#apigatewayurl)
* [appContainer](root.runtimeconfiguration.md#appcontainer)
* [appId](root.runtimeconfiguration.md#appid)
* [baseFrameUrl](root.runtimeconfiguration.md#baseframeurl)
* [basePath](root.runtimeconfiguration.md#basepath)
* [baseUrl](root.runtimeconfiguration.md#baseurl)
* [cdn](root.runtimeconfiguration.md#cdn)
* [changedProperties](root.runtimeconfiguration.md#changedproperties)
* [discovery](root.runtimeconfiguration.md#discovery)
* [environment](root.runtimeconfiguration.md#environment)
* [externalQueryParams](root.runtimeconfiguration.md#externalqueryparams)
* [featureFlags](root.runtimeconfiguration.md#featureflags)
* [gainsight](root.runtimeconfiguration.md#gainsight)
* [gqlEndpoint](root.runtimeconfiguration.md#gqlendpoint)
* [historyType](root.runtimeconfiguration.md#historytype)
* [hosts](root.runtimeconfiguration.md#hosts)
* [imsClientId](root.runtimeconfiguration.md#imsclientid)
* [imsEnvironment](root.runtimeconfiguration.md#imsenvironment)
* [imsInfo](root.runtimeconfiguration.md#imsinfo)
* [imsOrg](root.runtimeconfiguration.md#imsorg)
* [imsOrgName](root.runtimeconfiguration.md#imsorgname)
* [imsOrgs](root.runtimeconfiguration.md#imsorgs)
* [imsProfile](root.runtimeconfiguration.md#imsprofile)
* [imsToken](root.runtimeconfiguration.md#imstoken)
* [ioGatewayUrl](root.runtimeconfiguration.md#iogatewayurl)
* [ioRegionSpecificMap](root.runtimeconfiguration.md#ioregionspecificmap)
* [locale](root.runtimeconfiguration.md#locale)
* [metricsAppId](root.runtimeconfiguration.md#metricsappid)
* [metricsConfig](root.runtimeconfiguration.md#metricsconfig)
* [metricsEnv](root.runtimeconfiguration.md#metricsenv)
* [preferredLanguages](root.runtimeconfiguration.md#preferredlanguages)
* [sandbox](root.runtimeconfiguration.md#sandbox)
* [shellHeight](root.runtimeconfiguration.md#shellheight)
* [shellInfo](root.runtimeconfiguration.md#shellinfo)
* [shellSideNavCollapsed](root.runtimeconfiguration.md#shellsidenavcollapsed)
* [shellSideNavPresent](root.runtimeconfiguration.md#shellsidenavpresent)
* [shellSideNavWidth](root.runtimeconfiguration.md#shellsidenavwidth)
* [sourceEnvironment](root.runtimeconfiguration.md#sourceenvironment)
* [spaAppId](root.runtimeconfiguration.md#spaappid)
* [subOrg](root.runtimeconfiguration.md#suborg)
* [tenant](root.runtimeconfiguration.md#tenant)
* [tenantAppId](root.runtimeconfiguration.md#tenantappid)
* [theme](root.runtimeconfiguration.md#theme)
* [xqlGatewayUrl](root.runtimeconfiguration.md#xqlgatewayurl)

## Properties

### analytics

• `Optional` **analytics**: undefined \| { script: string ; solution: string  }

OMEGA Launch script properties

___

### apiGatewayUrl

•  **apiGatewayUrl**: string

Unified Shell API Gateway URL

___

### appContainer

•  **appContainer**: string

App Container

___

### appId

•  **appId**: string

Solution appId

___

### baseFrameUrl

•  **baseFrameUrl**: string

Solution iframe src url

___

### basePath

•  **basePath**: string

Base path of the baseUrl property, without tenant or URL context.

___

### baseUrl

•  **baseUrl**: string

Base URL

___

### cdn

•  **cdn**: string

Environment specific CDN string.

___

### changedProperties

•  **changedProperties**: keyof [RuntimeConfiguration](root.runtimeconfiguration.md)[]

List all properties changed in this configuration compared to the previous one sent

___

### discovery

•  **discovery**: boolean

If discovery URL

___

### environment

•  **environment**: string

Unified Shell's environment

___

### externalQueryParams

•  **externalQueryParams**: string

Query params

___

### featureFlags

• `Optional` **featureFlags**: Record<string, string\>

List of feature flags

___

### gainsight

• `Optional` **gainsight**: undefined \| { enabled: boolean ; productKey: string  }

Gainsight configuration.

___

### gqlEndpoint

• `Optional` **gqlEndpoint**: undefined \| string

Clients can pass in their local GQL endpoint

___

### historyType

•  **historyType**: \"HASH\" \| \"HISTORY\" \| \"SERVER\"

Solution History type

___

### hosts

• `Optional` **hosts**: string[]

Solution's list of multiple subdomains

___

### imsClientId

•  **imsClientId**: string

IMS Client ID

___

### imsEnvironment

•  **imsEnvironment**: string

IMS env

___

### imsInfo

•  **imsInfo**: ImsInfo

IMS Information

___

### imsOrg

•  **imsOrg**: string

Current IMS Org ID

___

### imsOrgName

•  **imsOrgName**: string

Current IMS Org Name

___

### imsOrgs

•  **imsOrgs**: Array<Record<string, ImsOrg\>\>

ImsOrg Interface

___

### imsProfile

• `Optional` **imsProfile**: [ImsProfile](ims.imsprofile.md)

User IMS Profile

___

### imsToken

•  **imsToken**: string

IMS Token

___

### ioGatewayUrl

• `Optional` **ioGatewayUrl**: undefined \| string

Adobe IO gateway URL used as a fallback in GQL call

___

### ioRegionSpecificMap

• `Optional` **ioRegionSpecificMap**: Record<string, string\>

Map of Adobe Io region specific endpoints.

___

### locale

•  **locale**: string

User Locale

___

### metricsAppId

• `Optional` **metricsAppId**: undefined \| string

Solution metricsAppId

___

### metricsConfig

•  **metricsConfig**: MetricsConfiguration

AdobeMetricsRuntime Configuration

___

### metricsEnv

• `Optional` **metricsEnv**: undefined \| string

Metrics environment (may differ from environment)

___

### preferredLanguages

• `Optional` **preferredLanguages**: string[]

List of languages from user's preferences

___

### sandbox

• `Optional` **sandbox**: [Sandbox](user.sandbox.md)

Current Sandbox

___

### shellHeight

•  **shellHeight**: number

Shell Height

___

### shellInfo

• `Optional` **shellInfo**: Record<string, any\>

Shell Info

___

### shellSideNavCollapsed

• `Optional` **shellSideNavCollapsed**: undefined \| false \| true

Is Side Nav collapsed?

___

### shellSideNavPresent

•  **shellSideNavPresent**: boolean

Is Side Nav enabled?

___

### shellSideNavWidth

•  **shellSideNavWidth**: number

Side Nav width

___

### sourceEnvironment

•  **sourceEnvironment**: string

Source environment

___

### spaAppId

• `Optional` **spaAppId**: undefined \| string

SPA pipeline app id

___

### subOrg

• `Optional` **subOrg**: Record<string, any\>

Sub Org

___

### tenant

•  **tenant**: string

Tenant ID

___

### tenantAppId

• `Optional` **tenantAppId**: undefined \| string

**`deprecated`** Solution GraphQL tenantAppId

___

### theme

•  **theme**: string

___

### xqlGatewayUrl

• `Optional` **xqlGatewayUrl**: undefined \| string

XQL gateway used for AEP specific queries
