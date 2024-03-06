Version Control
=====================

Guidance for Updating EC2 Instances Using AMIs and Launch Templates
-------------------------------

Step 1: Create a Machine from an AMI
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

1. **Login to AWS Console**: Access the AWS Management Console using your credentials.
   
2. **Select EC2 Service**: Navigate to the EC2 service from the AWS Console dashboard.

3. **Launch an Instance**:
   
   - Click on "Instances" in the left-hand navigation pane.
   - Choose "Launch Instances."
   - Select the appropriate AMI used for your load balancer.
   - Specify the instance type (e.g., t3a.micro) and configure other details accordingly.
   - Configure security groups, storage, and tags based on project requirements.
   - Review settings and launch the instance.

Step 2: Code Checkout and Validation
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

1. **SSH into the New Instance**:
   - Once the instance is running, SSH into it using the associated key pair.
   
2. **Code Checkout**:
   
   - Change to the relevant directory.
   - Use version control commands (e.g., git checkout) to pull the latest code.
   - Compile, build, or set up the application as needed.

3. **Validation**:
   
   - Run tests and perform validations to ensure the application functions correctly on the new instance.

Step 3: Create a New AMI
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

1. **In AWS Console**:
   
   - Navigate to the EC2 service.
   - Click on "Instances" in the left-hand navigation pane.
   - Select the instance you created.
   - Choose "Actions" and then "Create Image (AMI)."
   - Provide a descriptive name and description for the new AMI.
   - Click "Create Image."

Step 4: Update the Launch Template
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

1. **In AWS Console**:
   
   - Go to the EC2 service.
   - Click on "Launch Templates" in the left-hand navigation pane.
   - Select the launch template used for your Auto Scaling Group (ASG).
   - Edit the launch template.
   - Update the AMI ID with the newly created AMI.
   - Save the changes.

Step 5: Use ASG to Refresh Instances
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

1. **In AWS Console**:
   
   - Navigate to the EC2 service.
   - Click on "Auto Scaling Groups" in the left-hand navigation pane.
   - Choose the ASG you want to refresh.
   - Click “Instance Refresh” and then “Start Instance Refresh.”
   - Wait for a few minutes for the new instance to start.

By following these steps, you can efficiently update EC2 instances using AMIs and launch templates, ensuring that your application remains up-to-date with the latest changes.