# Deploy Azure VM with Ubuntu Linux and Nginx server

In this tutorial you will learn how to deploy a functioning web server on Azure VMs using Ubuntu OS and Nginx web server.

## Prerequisites

To complete this tutorial, you will need:

- Azure subscription
- Public SSH authentication key

Check the [Prerequisites](/docs/prerequisites.md) document how to obtain either.

## Launch the Instance

1. In [Azure portal](https://portal.azure.com) select **Create a resource**
2. Select **Ubuntu Server** among Popular resources
    - Alternatively, search for *Ubuntu* resource and select **Ubuntu Server**

### Complete the Basics page

1. Enter *your_server_name* in the **Name** field in the Basics section
2. Enter *ubuntu* in the **Username** field
3. Paste the *public key* string in PEM format into **SSH public key** field
    - Check [prerequisites](/docs/prerequisites.md) for a proper formatting of the public key
4. Enter *your_server_name* in the **Resource group** field and keep the selection on **Create New**
5. Select **OK** to proceed to *Choose a size* page

### Choose a size page

1. Select **B1s** or other similarly tiny virtual machine size
2. Select **Select** at the bottom of the page to proceed to *Settings* page

### Settings page

1. Click the drop-down under **Select public inbound ports**
2. Select **HTTP** and **SSH (22)**
3. Click **No Extensions** under *Extensions*
4. Click **Add extension** in *Extensions* pane
5. Select **Custom Script for Linux** in *New resource* pane
6. Click **Create** in *Custom Script for Linux* pane

#### Install Extension page

1. On your local computer create a new file named **script.sh**
2. Insert the following three lines into the file: 
```
#!/bin/bash
sudo apt install nginx -y
echo "<h1>Hello world from Azure VM!</h1>" | sudo tee /var/www/html/index.html
```
1. Save the **script.sh** file to your local disk
2. In Azure console, click **Select a file** field and choose the *script.sh* file from your local disk
3. Click **OK** at the bottom of the page to return to Extensions pane
4. Click **OK** again to close the Extensions pane
5. Click **OK** for the third time to close the Settings pane

### Create page

1. If configuration was entered correctly, the top of the pane will display **Validation passed**.
2. Select **Create** at the bottom of the page to start the deployment. It will take 5-7 minutes to deploy the instance.

## Test the web server

1. Go to the **Azure dashboard** section on the left and wait for *your_server_name* deployment to complete and is in **Running** state.
2. Select **your_server_name**
3. Select and copy (ctrl-c) **Public IP address** of the newly created instance
4. Use the browser to load your functioning public web page using **http://your_IP_address**

## `SUCCESS!`

## Clean-up tasks

1. Go to the **Resource groups** section of Azure portal
2. Right-click on the line with your *your_server_name* resource group
3. Select **Delete resource group**
4. Type **your_server_name** into the Resource group field
5. Acknowledge by selecting **Delete** at the bottom of the page