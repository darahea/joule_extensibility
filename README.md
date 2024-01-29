# joule-functions-example
This is a reference for an assistant build with the Joule Functions approach.

## Content

```json5
└── example_assistant/ // Assistant root
    ├── da.sapdas.yaml  // Assistant definition combining capabilities
    └── weather_capability/ // Capability root
        ├── functions // Root for functions
        ├── scenarios // Root for scenarios
        └── capability.sapdas.yaml // Capability definition with System Aliases
```


## Use-Cases

### Weather Fetching

Fetching weather for a city and returning a response based on scripting.

![weather_example.png](weather_example.png)
