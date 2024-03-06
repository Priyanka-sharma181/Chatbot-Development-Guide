
Configure Basic Settings
------------------------

Now that you have created your new bot and you have the bot ID. Let's move to the starter kit and make a few updates.

.. note::
   Make sure before moving to the below steps, you have installed the required tools. If not then follow this `guide <installation.rst>`_

Make Changes In Starter Kit
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
1. Open the cloned respository in your preferred code editor
2. Navigate to **.env.text** file and change it's name to **.env**. Update the value of .env file with your actual data.
   
   .. image:: ../images/deployement_images/env_file.png
      :alt: Deployment Structure
      :width: 2000
      :height: 200
      :align: left
         
3. Now navigate to the **i18n** folder and then access the **en** and **hn** files. Update the welcome message as required and save the changes. Here we will add "Hello World" to demonstrate
   
   .. image:: ../images/create_bot_images/i8-en.png
      :alt: Deployment Structure
      :width: 2000
      :height: 200
      :align: left
         

Setup Webhook URL
^^^^^^^^^^^^^^^^^^^^^
1. Access to this `URL <https://dashboard.ngrok.com/signup>`_ and create an acco on **Ngrok**. Complete the sign-up process and get your authorization token.
   
   - Open the terminal and enter this command: ``ngrok config add-authtoken <TOKEN>``. Replace <Token> with the authorization token.
  
2. Open terminal and run this command: ``ngrok http 3000``. This will generate a **Forwarding** URL. Copy and save this.
   
   .. image:: ../images/other_images/config_settings.png
        :alt: Deployment Structure
        :width: 2000
        :height: 200
        :align: left
   
3. Open the Postman or any other API platform
4. Create a new PUT request and add this API ``https://v1-api.swiftchat.ai/api/bots/<bot-id>/webhook-url``in the url placeholder. Don't forget to add your bot-id.
5. Add the Bearer API-Key in the authorization tab
6. Add this in the body
   
   .. code-block:: json

        {    
        "webhook_url": "<Forwarding url/message>"
        }
------------------------