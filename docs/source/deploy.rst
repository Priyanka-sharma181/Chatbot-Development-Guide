Deployment Procedure
====================
To view the functioning Chatbot, you must host the NodeJS application on a remote server and configure the SwiftChatbot application portal to connect with the NodeJS application.

Steps to deploy
------------------------

1. **Setup EC2 Instance:** To set up an EC2 instance (if not already done or if you wish to set up a new instance) in the ap-south-1 region with Ubuntu AMI, 16 GB storage, and t2.small compute power, follow this: `Ec2 Instance Setup Guide <ec2_instance.html>`_

.. note::
    Download the generated .pem file and store it securely on your local system. This file will be used for SSH access to the EC2 instance.

2. SSH into Instance: Use the following command to SSH into the instance with the provided .pem file:

``` ssh -i "<Your_PEM_file_name>" <Your_Host_IP_address_or_Domain_Name> ```

3. To set up the necessary software components, follow these steps:

- Update and upgrade the system packages:
```
sudo apt update
sudo apt upgrade
```

- Install Node.js, npm, Nginx, and PM2:
```
sudo apt install -y nodejs npm nginx
sudo npm install -g pm2
```

- (Optional) Install MySQL if you prefer setting up a local MySQL instance instead of using AWS RDS:
```
sudo apt install -y mysql-server
```

- Configure the MySQL root password:
```
sudo mysql -e "ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'mypassword';"
```
.. note::
    If you are using AWS RDS, create a new user and grant all permissions. These credentials will be used when setting up the .env file later.

.. tip::
    If the root password does not change using the command above, follow the instructions provided `here <https://stackoverflow.com/questions/42421585/default-password-of-mysql-in-ubuntu-server-16-04>`.

