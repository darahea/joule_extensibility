# Search Products - Step 4: Deploy the assistant and test the "products" capability

In this step, we will deploy the assistant test our new weather capability.

## Preview

**TODO: Add screenshot of running assistant**

*Our assistant is now capable of fetching the weather for a given location.*

## Steps

A more detailed description of the login and deployment with the joule CLI can be found in the [Hello World - Step 3](../../helloworld/step3/index.md) tutorial.

### Deploy your assistant

1. Run the following command in your `capabilities` folder to deploy your assistant:
```bash
joule deploy -c -n "products"
```

By specifying the `-c` option, you will implicitly compile the assistant before deploying it.

Specify a name parameter with the `-n` option to give your assistant a name. This name will be used to identify your assistant in the Joule server and help to avoid conflicts with other assistants running on the same account.

### Test your assistant in the standalone web client:

1. Run the following command to open the standalone web client:
```bash
joule launch products
```
2. A Browser will open with the joule web client. You can now test your assistant in the chat window.
3. Type "Search for products" to call the new capability.

**TODO: Add a useful example query here**

* [Back to Overview](../index.md)

## Related Information 

[Test the capability](https://help.sap.com/docs/joule/service-guide/test-capability)
