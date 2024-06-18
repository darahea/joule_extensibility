# Hello World - Step 2: Create a new assistant and the "hello world" capability

In this step, we will create a new digital assistant.

*Please note that the Joule IDE Extension does not support the latest schema and Joule functions yet. 
For the moment, we will manually create the needed assets and update the tutorial later on when this functionality is available.*  

## Preview


## Steps

### capabilities/da.sapdas.yaml (NEW)

```yaml
schema_version: 3.0.0
name: joule_assistant
capabilities:
  - type: local
    folder: ./helloworld_capability
```

We create a basic configuration file for our digital assistant. It defines a set of capabilities that the assistant can use.

1. Create a new folder in your project root directory and name it `capabilites`.
2. Add a new file `da.sapdas.yaml` in the newly created folder
2. Set the schema version to `3.0.0`
3. Set the name to `joule_assistant`
4. Add a new capability of type `local` and set the folder to `./helloworld_capability`

### capabilities/helloworld/capability.sapdas.yaml (NEW)

```yaml
schema_version: 3.0.0

metadata:
  namespace: com.sap.das.demo
  name: helloworld_capability
  version: 1.0.0
  display_name: "Hello World Capability"
  description: "This capability says hello world."
```

We add a new hello world capability to our assistant by specifying the display name and the description:

1. Create a new subfolder in your `capabilites` folder and name it `helloworld`.
2. Add a new file `capability.sapdas.yaml` in the newly created folder
3. Copy the content above into the file

### capabilities/helloworld/scenarios/hello_world.yaml (NEW)

```yaml
description: This function says hello world or the name of the user

slots:
- name: name
  description: The name of the person to be greeted

target:
type: function
name: helloworld/say_hello
```
Next, we define the scenario for the capability. It contains the parameters (slots) and the joule function to call.
Be sure to provide a meaningful description for the function as this parameter will be used by the dialog model to find the function.

1. Create a new folder in your `helloworld` folder and name it `scenarios`.
2. Create a new file `hello_world.yaml` in the newly created folder
1. Define a slot `name` that can be filled with a name in the prompt
2. Define the target function `helloworld/say_hello` that will be called when the scenario is triggered

### capabilities/helloworld/functions/helloworld/hello_world.yaml (NEW)

```yaml
parameters:
  - name: name
action_groups:
  - condition: name != null
    actions:
      - type: message
        message: 
            type: text 
            content: "Hello <? name ?> from joule function!"
  - condition: name == null
    actions:
      - type: message
        message:
            type: text
            content: "Hello World from joule function!"
```

Finally, we add the joule function that will show the hello world message to the user. We use the `name` parameter to personalize the message. If it is filled, we greet the user with the name provided. If not, we just show a general "Hello World" message. 

1. Create a new folder in your `helloworld` folder and name it `functions`.
2. Create a new folder `helloworld` in the newly created folder that will contain all functions for the hello world capability.
3. Create a new file `hello_world.yaml` in the folder `helloworld`
4. Define a parameter `name` as an input for the function that will be connected to the slot above
5. Define two action groups that will be executed based on the condition if the name is provided or not
6. Add output messages that will be displayed in the chat window for both scenarios

## Summary

We have created an assistant and a function to our project. The overall project structure should look like this:

```
└── capabilities/ // assistant root
    ├── da.sapdas.yaml  // assistant definition combining capabilities
    └── helloworld/ // capability root
        ├── functions // root for functions
            └── helloworld/ // function folder
                └── say_hello.yaml // hello world function
        ├── scenarios // root for scenarios
            └── hello_world.yml // hello world scenario
        └── capability.sapdas.yaml // capability definition
```

## Related Information 

[Build a capability](https://help.sap.com/docs/joule/service-guide/build-capability)