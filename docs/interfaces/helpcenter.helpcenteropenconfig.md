**[@adobe/exc-app](../README.md)**

> [Globals](../README.md) / [helpCenter](../modules/helpcenter.md) / HelpCenterOpenConfig

# Interface: HelpCenterOpenConfig

## Hierarchy

* **HelpCenterOpenConfig**

## Index

### Properties

* [config](helpcenter.helpcenteropenconfig.md#config)
* [selectedTab](helpcenter.helpcenteropenconfig.md#selectedtab)

## Properties

### config

•  **config**: { subject: string ; type: \"CONTEXTUAL\_FEEDBACK\_SUBMISSION\"  }

Configuration for Help Center fields when opened.

#### Type declaration:

Name | Type | Description |
------ | ------ | ------ |
`subject` | string | String that prepopulates the subject field in the Help center feedback section. |
`type` | \"CONTEXTUAL\_FEEDBACK\_SUBMISSION\" | Type of feedback. Only CONTEXTUAL_FEEDBACK_SUBMISSION is supported, meaning that the Help Center feedback tab will be opened. |

___

### selectedTab

•  **selectedTab**: \"feedback\" \| \"support\"

Selected Help Center Tab.
