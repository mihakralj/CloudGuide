# Deploy GCP Function with js code

In this tutorial you will learn how to deploy a simple GCP .js function that responds to http requests.

## Prerequisites

To complete this tutorial, you will need:

- GCP subscription
- [(Free) Google account](https://cloud.google.com/free/)

## Create GCP Function

1. In [GCP console](https://console.cloud.google.com) select **Cloud Functions**
2. Select **Create function**
3. Enter **your_function_name** in the *Name* field
4. Select and copy (Ctrl-c) the **function URL** 
5. Paste the code below over the existing javascript example in the *Source code* field
 
```
exports.helloWorld = (req, res) => {
    res.status(200).send("<h1>Hello world from GCP function!</h1>");
}
 ```

 5. Select **Create** at the bottom of the page

## Test the Function

1. Use the browser to load your function page using the **function URL**

## `SUCCESS!`

## Clean-up tasks

1. In [GCP console](https://console.cloud.google.com) select **Cloud Functions**
2. Select *your_function_name*  and click **Delete** at the top of the page
3. Select **Delete** to confirm the removal of the instance
