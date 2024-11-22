# joule-functions-example

In this repository, you will find a reference for an assistant built with the Joule Functions approach.
We will explain how to define a scenario using an LLM-based dialog management and response generation.

For instructions on all three examples please check the corresponding tutorials below.
If you want to adapt or build content on your own, consider the [SAP Help documentation](https://help.sap.com/docs/joule/service-guide/development?locale=en-US).

**Disclaimer:** Joule Functions are supported with spec version `3.x.x` and will not be made available on staging landscape, as it's not a productive landscape and planned to be decommissioned. Please use internal prod landscape instead, which is now available on BTP Canary `eu12` - so you can subscribe it in the same subaccount you're already using for staging and then remove the staging subscription. The required entitlements are showing up as `das-application-canary` and `das-service-canary` in SAP BTP Control Center. If you are unsure on which landscape, type the command `joule status` and check the API url.

## Content

```
└── capabilities/ // assistant root
    ├── weather // a capability calling an external weather API and presenting results via response generation
    └── products // a more complex example showing products from an OData service
    
```
