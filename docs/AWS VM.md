---
typora-copy-images-to: ..\images
---

# Deploy AWS VM with Ubuntu Linux and Nginx server

In this tutorial , you learn how to deploy a functioning web server on AWS VMs using Ubuntu OS and Nginx web server.

## Prerequisites

To complete this tutorial, you will need:

- AWS subscription
- Pair of SSH authentication keys

Check the [Prerequisites](/docs/prerequisites.md) document how to obtain either.

## Import SSH keys

1. Log to AWS console
2. Go to the **EC2 section** under Compute Services
3. Select **Key Pairs** under Network & Security select Key Pair
4. Select **Import Key Pair**
5. Enter the chosen name for the Key pair
6. Insert your public key into the contents window
7. Select **Import**

![AWS_importkeypair](../images/AWS_importkeypair.jpg)