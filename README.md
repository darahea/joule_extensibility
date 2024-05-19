# joule-functions-example
This is a reference for an assistant build with the Joule Functions approach.

If you want to adapt or build content on your own, consider the [Content Building Guideline](https://sap.sharepoint.com/:b:/r/teams/JouleFunctionsPilot/Shared%20Documents/General/Content_Building_Guideline_Joule_Functions.pdf?csf=1&web=1&e=OirLGA).

## Content

```
└── example_assistant/ // Assistant root
    ├── da.sapdas.yaml  // Assistant definition combining capabilities
    └── weather_capability/ // Capability root
        ├── functions // Root for functions
        ├── scenarios // Root for scenarios
        └── capability.sapdas.yaml // Capability definition with System Aliases
```


> A more complex example for the flight search can be found in a dedicated [branch](https://github.tools.sap/DAS-Samples/joule-functions-example/tree/fb_flight_search).

## Use-Cases

### Weather Fetching

Fetching weather for a city and returning a response based on scripting.

![weather_example.png](weather_example.png)


## Setup

Follow the following steps to setup the example assistant.
As a prerequisite you need to have all [prerequisite steps done as described](https://github.tools.sap/DAS-Samples/da-mc-developers-hands-on/tree/1-Setting-up-the-environment) resulting in the following steps achieved:
- Subaccount with subscription to Digital Assistant
- IDE Extension & CLI installed 

> Minimal CLI version required: **1.3.8**
>
> Minimal IDE Extension version required for IDE support: **1.1.36**

### Destination

Create a destination with the following settings in your subaccount:

```properties
URL=https://api.weather.com/v3
Name=WEATHER
ProxyType=Internet
Type=HTTP
Authentication=NoAuthentication
```

Click on "New Property" to add the propery `URL.queries.apiKey` with value `c322ef22435d40bfa2ef22435df0bfbe`. This will automatically add the API Key as additional query parameter to all API calls.

### Compilation and Deployment

Run `sapdas deploy -c -n <assistant_name>` to compile and deploy the assistant to your subaccount.
Check out [the initial guide for our CLI tool](https://github.tools.sap/DAS-Samples/da-mc-developers-hands-on/tree/4-Play-with-your-Digital-Assistant) for more information.


:information_source: Most parts of our [SAP Help documentation](https://help.sap.com/docs/joule/service-guide/development?locale=en-US) are still relevant for you to get started.
