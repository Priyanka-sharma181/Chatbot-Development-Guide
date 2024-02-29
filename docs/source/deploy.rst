Deployment Proceedure
====================
To view the functioning Chatbot, you must host the NodeJS application on a remote server and configure the SwiftChatbot application portal to connect with the NodeJS application.

Steps to deploy
------------------------

1. Setup EC2 Instance: To set up an EC2 instance (if not already done or if you wish to set up a new instance) in the ap-south-1 region with Ubuntu AMI, 16 GB storage, and t2.small compute power, follow this guide: `EC2 Instance Setup <ec2_instance.rst>`_

Launch an EC2 instance in the ap-south-1 region with Ubuntu AMI, 16 GB Storage, and t2.small Compute power.
When creating the instance, generate a Key-Value pair named "khabri-media-bot" to access the instance. Store the generated .pem file securely on your system.

