**[@adobe/exc-app](../README.md)**

> [Globals](../README.md) / [helpCenter](../modules/helpcenter.md) / HelpCenterConfig

# Interface: HelpCenterConfig

## Hierarchy

* **HelpCenterConfig**

## Index

### Properties

* [featured](helpcenter.helpcenterconfig.md#featured)
* [questions](helpcenter.helpcenterconfig.md#questions)
* [recommendations](helpcenter.helpcenterconfig.md#recommendations)
* [resources](helpcenter.helpcenterconfig.md#resources)

## Properties

### featured

• `Optional` **featured**: Array<{ href: string ; label: string ; path: string \| Array<string\>  }\>

Adds help links to the *featured* section of the help center.

___

### questions

• `Optional` **questions**: Array<string\>

If the solution wants to simulate "Frequently asked questions", it can provide them as an array of strings. These appear as the user starts typing in the Search field.

___

### recommendations

• `Optional` **recommendations**: undefined \| { enabled: boolean ; terms: Array<{ path: string ; term: string  }\>  }

Customizes *for you* section of the help center.

___

### resources

• `Optional` **resources**: Array<{ href: string ; label: string  }\>

Overrides default links present in *resources* section. Product owners are advised to supply custom resources links to ensure greater relevance.
