# Deploy GCP VM with Ubuntu Linux and Nginx server

In this tutorial you learn how to deploy a functioning web server on GCP VMs using Ubuntu OS and Nginx web server.

## Prerequisites

To complete this tutorial, you will need:

- GCP subscription
- Public SSH authentication key

Check the [Prerequisites](/docs/prerequisites.md) document how to obtain either.

## Launch the Instance

1. In [GCP console](https://console.cloud.google.com) hover over **Compute Engine** and select **VM instances**
2. Select **Create Instance** at the top of the page
3. Select **Change** in *Boot disk* section
4. Choose (any) **Ubuntu** image at the *Boot disk* page
5. Click **Select** at the bottom of the page to close the *Boot disk* page
6. Select **Allow HTTP traffic** in *Firewall* section
7. Click **Management, disks, networking, SSH keys** to expand advanced settings
8. Insert into **Startup script** the following configuration script:

```
#!/bin/bash
sudo apt install nginx -y
echo "<h1>Hello world from GCP VM!</h1>" | sudo tee /var/www/html/index.html
```
9. Open **SSH Keys** section and paste the private key into provided field
    - **Note:** GCP requires public keyto be  formatted in rsa-key form, check [prerequisites](/docs/prerequisites.md) for a proper formatting.
10. Select **Create** at the bottom of the page and start the deployment. It will take 1-2 minutes to initiate the instance.

