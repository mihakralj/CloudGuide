# Deploy Azure VM with Ubuntu Linux and Nginx server

In this tutorial you will learn how to deploy a functioning web server on Azure VMs using Ubuntu OS and Nginx web server.

## Prerequisites

To complete this tutorial, you will need:

- Azure subscription
- Pair of SSH authentication keys

Check the [Prerequisites](/docs/prerequisites.md) document how to obtain either.

## Launch the Instance

1. In [Azure portal](https://portal.azure.com), select **Create a resource**
2. Select **Ubuntu Server** among Popular resources
    - Alternatively, search for *Ubuntu* resource and select **Ubuntu Server**

### Complete the Basics page

1. Enter *your_server_name* in the **Name** field in the Basics section
2. Enter *ubuntu* in the **Username** field
3. Paste the *public key* string into **SSH public key** field
    - Check [prerequisites](/docs/prerequisites.md) for a proper formatting of the public key
4. Enter *your_server_name* in the **Resource group** field and keep the selection on **Create New**
5. Select **OK** to proceed to *Choose a size* page

### Choose a size page

1. Select **B1s** or other similarly tiny virtual machine size
2. Select **Select** at the bottom of the screen to proceed to *Settings* page

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
echo "<h1>Hello world from AWS VM!</h1>" | sudo tee /var/www/html/index.html
```
3. Save the **script.sh** file
4. In Azure console, click **Select a file** field and choose the *script.sh* file from your local disk
5. Click **OK** at the bottom of the screen to return to Extensions pane

7. dsds
8. dsds
9. 