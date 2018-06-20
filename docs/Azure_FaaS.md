# Deploy Azure Function with js code

In this tutorial you will learn how to deploy a simple Azure .js function that responds to http requests.

## Prerequisites

To complete this tutorial, you will need:

- Azure subscription or [free Azure account](https://azure.microsoft.com/free/?ref=microsoft.com&amp;utm_source=microsoft.com&amp;utm_medium=docs&amp;utm_campaign=visualstudio )

## Create Azure Function

1. In [Azure portal](https://portal.azure.com) select **Create a resource**
2. Select **Serverless Function App** among Popular resources
    - Alternatively, search for *Function* resource and select **Function App**

### Function App page

1. Enter *your_function_name* in the **App Name** field
    - **Note:** the name of your function has to be *globally unique*; Azure will let you know if the chosen name is already taken.
2. Select **Create** at the bottom of the page to start the deployment. It will take 2-3 minutes to deploy the serveless function.

## Create an Azure Function

1. In [Azure portal Dashboard](https://portal.azure.com) select *your_function_name* running function app
2. Select **Functions** category in the first pane and click the black **+ New function** *at the top of the second pane*
    -   **Note:** do not click the blue **+** in the first pane. The *Quick route* actually requires more steps. If you clicked the blue **+** and got to *Get started quickly with a premade function*, click again on the **Functions** in the left pane and then click the *black* plus next to **New function** in the right pane.
1. Select **HTTP trigger** template
2. Choose **JavaScript** as a *Language* in the *HTTP trigger* pane
3. Choose **Anonymous** as the *Authorization level* of HTTP trigger
4. Select **Create** to create a new function
5. Paste the code below over the existing javascript example

```
module.exports = (context, req) => {
context.bindings.res = {
    body: `<h1>Hello world from Azure function!</h1>`,
    headers: { 'content-type': 'text/html' }
  }
  context.done()
}
```
6. Select **Save and Run** and check the output in the bottom right corner of the page
7. Select **</> Get function URL** at the top of the page
8. Select and copy (Ctrl-c) the function URL, close the window by clicking the **x** in the top right corner

## Test the Function

1. Use the browser to load your function page using the **Azure function URL**

## `SUCCESS!`

## Clean-up tasks

1. Go to the **Resource groups** section in Azure portal 
2. Right-click on the line with your *your_function_name* resource group
3. Select **Delete resource group**
4. Type **your_function_name** into the Resource group field
5. Acknowledge by selecting **Delete** at the bottom of the page