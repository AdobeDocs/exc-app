**[@adobe/exc-app](../README.md)**

> [Globals](../README.md) / [network](../modules/network.md) / FetchCondition

# Interface: FetchCondition

Defines the conditions when certain data can be fetched.
When conditions are not met, default data will be returned but not cached.

## Hierarchy

* **FetchCondition**

## Index

### Properties

* [serviceCodes](network.fetchcondition.md#servicecodes)

## Properties

### serviceCodes

• `Optional` **serviceCodes**: string \| string[]

Service Codes that needs to be present (For the current org) in order to execute the query.
This is useful when a query only makes sense if a certain product is provisioned for the current user.
