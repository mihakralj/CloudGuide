# Deploy AWS VM with Ubuntu Linux and Nginx server

In this tutorial , you learn how to deploy a functioning web server on AWS VMs using Ubuntu OS and Nginx web server.

## Prerequisites

To complete this tutorial, you will need:

- AWS subscription
- Pair of SSH authentication keys

Check the [Prerequisites](/docs/prerequisites.md) document how to obtain either.

## Import SSH keys

1. Log to AWS console
2. Go to the **EC2 **section under Services - Compute Services
3. Select **Key Pairs** under Network & Security select Key Pair
4. Select **Import Key Pair**
5. Enter the chosen name for the Key pair
6. Insert your public key into the contents window
7. Select **Import** <details><summary>Show me how</summary>![AWS_importkeypair](../images/AWS_importkeypair.jpg)</details>

## Launch Instance

8. Go to the **EC2 **section under Services - Compute Services
9. Select **Launch Instance**
10. Select **Ubuntu Server** at Step 1
11. Select **Next: Configure Instance Details** at Step 2 (keep *t2.micro* as a default instance type)
12. Extend the **Advanced Details** section at the bottom of the screen at Step 3
13. Insert into **User data** field the following configuration script:

```bash
#!/bin/bash
sudo apt install nginx -y
echo "<h1>Hello world from AWS VM!</h1>" | sudo tee /var/www/html/index.html
```

14. Select **Next: Add Storage** at the bottom of the screen of Step 3
15. Select **Next: Add Tags** at Step 4
16. Select **Next: Configure Security Group** at Step 5
17. Select **Add Rule** and select HTTP in a drop-down box for the new rule <details><summary>Show me how</summary>![AWS_httpport](../images/AWS_httpport.jpg)</details>

18. Select **Review and Launch** at the bottom of the screen of Step 6
19. Select **Launch** at Step 7
20. Select your imported key at **Select a key pair** and check the checkbox <details><summary>Show me how</summary>![AWS_keypair](../images/AWS_keypair.jpg)</details>

21. Select **Launch Instances** and let the process take 3-5 minutes to initiate the instance.

## Test the web server

1. Go to the **EC2 **section under Services - Compute Services
2. Select **Instances** under Instances
3. Check the IP address of the newly created instance
