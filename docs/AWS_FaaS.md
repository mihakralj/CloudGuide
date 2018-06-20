# Deploy AWS Lambda Function with js code

In this tutorial you will learn how to deploy a simple AWS Lambda function function that responds to http requests.

## Prerequisites

To complete this tutorial, you will need:

- AWS subscription or [free AWS account](https://aws.amazon.com/free/)

## Create AWS Lambda Function

1. Select **Lambda** section under Compute in [AWS console](https://console.aws.amazon.com)
2. Select **Create a function**
3. Enter **your_function_name** in the *Name* field
4. Select **Create new role from template(s)** in the *Role* selector
5. Enter **your_function_role_name** in the *Role name* field
6. Select **Create function** at the bottom of the page
 
### Lambda Configuration

1. Scroll down the page and paste the code below over the existing javascript example

```
exports.handler = (event, context, callback) => {
const response = {
  headers: {'Content-Type': 'text/html',},
  body: `<h1>Hello world from AWS Lambda function!</h1>`,
};
callback(null, response);
};
```

2. Scroll back up the page and select **API Gateway** under *Add triggers* on the left side of the page
3. Select **Create a new API** in the *API* selector
4. Enter **your_API_name** in the *API name* field
5. Enter **prod** in the *Deployment stage* field
6. Select **Open** in the *Security* selector
7. Select **Add** at the bottom of the page
8. Select **Save** at the top of the same page
9. Select **your_API_name** under *API Gateway* at the bottom left of the page

##  API Gateway Configuration

1. Select **Stages** on the left side
2. Expand **prod** stage by clicking on the :arrow_forward: in the *Stages* pane
3. Select **GET** method
4. Select and copy (Ctrl-c) the **Invoke URL**

## Test the Function

1. Use the browser to load your function page using the **Invoke URL**

## `SUCCESS!`

## Clean-up tasks

1. Under **Services** drop-down menu on the top select **Lambda** under *Compute*
2. Select **your_function_name**
3. Under **Actions** frop-down menu select **Delete function**
4. Select **Delete**
5. Under **Services** drop-down menu on the top select **API Gateway** (scroll down to the bottom of the page, API Gateway is in the section *Networking & Content Delivery*)
6. Select **your_API_name**
7. Under **Actions** frop-down menu select **Delete API**
8. Enter **your_API_name** and select **Delete API**
9. Under **Services** drop-down menu on the top select **IAM** under *Security, Identity & Compliance*
10. On the left side select **Roles**
11. Select **your_function_role_name** at the bottom of the page
12. Select **Delete role** in the top right of the page
13. Confirm by selecting **Yes, delete**