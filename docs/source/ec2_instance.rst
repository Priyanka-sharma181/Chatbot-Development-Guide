Steps To Setup EC2 Instance
====================

To set up an EC2 instance, follow these steps:

1. **Sign in to AWS Console**: Log in to your AWS Management Console.

2. **Navigate to EC2 Dashboard**: Go to the EC2 dashboard.

3. **Launch Instance**: Click on the "Launch Instance" button to begin the process of launching a new EC2 instance.

4. **Choose AMI**: Select the Ubuntu AMI from the available options.

5. **Choose Instance Type**: Choose the t2.small instance type for the compute power.

6. **Configure Instance**: Configure the instance settings, including the network, subnet, and storage. Set the storage to 16 GB.

7. **Add Tags (Optional)**: Optionally, add tags to your instance for better organization and management.

8. **Configure Security Group**: Configure the security group to allow inbound traffic on the necessary ports (e.g., HTTP, HTTPS) for your SwiftChatbot application.

9. **Review Instance Launch**: Review your instance details and settings to ensure everything is configured correctly.

10. **Generate Key Pair**: When prompted to generate a key pair for accessing the instance, provide a suitable name such as "swiftchat-bot" or "chatbot-instance".

11. **Download Key Pair**: Download the generated .pem file and store it securely on your local system. This file will be used for SSH access to the EC2 instance.

12. **Launch Instance**: After reviewing and confirming your settings, click on the "Launch Instance" button to launch the EC2 instance.

Once your EC2 instance is launched, you can proceed to configure it for hosting your SwiftChatbot application. Ensure that you follow the necessary steps to secure your instance, including setting up firewalls, configuring access permissions, and regularly updating your software to protect against security vulnerabilities.