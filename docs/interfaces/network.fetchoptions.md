**[@adobe/exc-app](../README.md)**

> [Globals](../README.md) / [network](../modules/network.md) / FetchOptions

# Interface: FetchOptions

## Hierarchy

* **FetchOptions**

## Index

### Properties

* [auth](network.fetchoptions.md#auth)
* [excludeSandbox](network.fetchoptions.md#excludesandbox)
* [excludeSandboxType](network.fetchoptions.md#excludesandboxtype)
* [maxRetries](network.fetchoptions.md#maxretries)
* [metadata](network.fetchoptions.md#metadata)
* [scope](network.fetchoptions.md#scope)
* [totalFetchTime](network.fetchoptions.md#totalfetchtime)

## Properties

### auth

• `Optional` **auth**: \"Header\" \| \"Body\"

A boolean value indicating whether to add Authentication token, API Key to the request.

___

### excludeSandbox

• `Optional` **excludeSandbox**: undefined \| false \| true

**`deprecated`** excludeSandbox should be replaced with scope

___

### excludeSandboxType

• `Optional` **excludeSandboxType**: undefined \| false \| true

**`deprecated`** excludeSandboxType should be replaced with scope

___

### maxRetries

• `Optional` **maxRetries**: undefined \| number

Number indicating how many fetch attempts should be made using exponential backoff.

___

### metadata

• `Optional` **metadata**: [DefaultMetaData](network.defaultmetadata.md)

___

### scope

• `Optional` **scope**: [FetchScope](../enums/network.fetchscope.md)

Specify the headers to be added to the request

___

### totalFetchTime

• `Optional` **totalFetchTime**: undefined \| number

Number in ms indicating the maximum amount of time taken by the the fetch request plus any
exponential backoff retry requests before aborting.
