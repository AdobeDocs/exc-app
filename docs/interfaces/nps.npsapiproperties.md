**[@adobe/exc-app](../README.md)**

> [Globals](../README.md) / [nps](../modules/nps.md) / NpsApiProperties

# Interface: NpsApiProperties

## Hierarchy

* **NpsApiProperties**

  ↳ [Nps](nps.nps-1.md)

## Index

### Properties

* [config](nps.npsapiproperties.md#config)

## Properties

### config

•  **config**: { enabled?: undefined \| false \| true ; sampling?: undefined \| number ; showToAdobeUsers?: undefined \| false \| true  }

An object of nps configuration attributes for solution.
By default the NPS widget is disabled. In order to enable NPS for a solution, the enabled key in the solution configuration should be set to true.
NPS configuration also contains a sampling key which describes the percentage of users that will see the NPS widget.
Whether NPS will be shown to Adobe users depends of the value of 'showToAdobeUsers' key. It is set to true by default.

#### Type declaration:

Name | Type | Description |
------ | ------ | ------ |
`enabled?` | undefined \| false \| true | Flag that enables nps for solution. |
`sampling?` | undefined \| number | Number that shows percent of user logins that can show nps. |
`showToAdobeUsers?` | undefined \| false \| true | Flag that enables showing nps survey to adobe users. |
