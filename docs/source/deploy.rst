Deployment Procedure
====================
To view the functioning Chatbot, you must host the NodeJS application on a remote server and configure the SwiftChatbot application portal to connect with the NodeJS application.

Steps to deploy
------------------------

1. **Setup EC2 Instance:** To set up an EC2 instance (if not already done or if you wish to set up a new instance) in the ap-south-1 region with Ubuntu AMI, 16 GB storage, and t2.small compute power, follow this guide: 

.. toctree::
   ec2_instance.rst

.. note::
    Download the generated .pem file and store it securely on your local system. This file will be used for SSH access to the EC2 instance.

2. SSH into Instance: Use the following command to SSH into the instance with the provided .pem file:

```
bash 
ssh -i "<Your_PEM_file_name>" <Your_Host_IP_address_or_Domain_Name>
```
