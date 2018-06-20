# Deploy GCP VM with Ubuntu Linux and Nginx server

In this tutorial you learn how to deploy a functioning web server on GCP VMs using Ubuntu OS and Nginx web server.

## Prerequisites

To complete this tutorial, you will need:

- GCP subscription
- Public SSH authentication key

Check the [Prerequisites](/docs/prerequisites.md) document how to obtain either.

## Launch the Instance

1. In [GCP console](https://console.cloud.google.com) hover over **Compute Engine** and select **VM instances**
2. Select **Create Instance**
3. Enter **your_server_name** in the *Name* field
4. Select **Change** in *Boot disk* section
5. Choose (any) **Ubuntu** image at the *Boot disk* page
6. Click **Select** at the bottom of the page to close the *Boot disk* page
7. Select **Allow HTTP traffic** in *Firewall* section
8. Click **Management, disks, networking, SSH keys** to expand advanced settings
9. Insert into **Startup script** the following configuration script:

```
#!/bin/bash
sudo apt install nginx -y
echo "<h1>Hello world from GCP VM!</h1>" | sudo tee /var/www/html/index.html
```
9. Open **SSH Keys** section and paste the private key into provided field
    - **Note:** GCP requires public keyto be  formatted in rsa-key form, check [prerequisites](/docs/prerequisites.md) for a proper formatting.
10. Select **Create** at the bottom of the page and start the deployment. It will take 1-2 minutes to initiate the instance.

## Test the web server

1. Wait for *your_server_name* deployment to complete and is in **Running** state.
3. Select and copy (ctrl-c) the **Extenrla IP** address of the newly created instance
4. Use the browser to load your functioning public web page using **http://your_IP_address**

## `SUCCESS!`

## Clean-up tasks

1. Select *your_server_name* instance and click **Delete** at the top of the page
3. Select **Delete** to confirm the removal of the instance
