Hello World!
------------------

In this tutorial, you'll create and publish your first bot onto Swiftchat. Following are the high level steps:

1. Create Swiftchat business account
2. Setup a Bot in Swift chat
3. Clone the repo "Chatbot Starter Kit"
4. Host the bot locally using ngrok
5. Add webhook url on Bot dashboard

1. Create Swiftchat Business Account
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
If you've not setup a Swiftchat account yet, please follow the :ref:`instructions here <swiftchat_registration>`. You should also :ref:`obtain your API Key <obtraining_api_keys>` which will be used to call Swiftchat APIs.

2. Setup a Bot in Swiftchat
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
To publish our bot on Swiftchat, we need to setup a Bot on Swiftchat Dashboard. Please follow the :ref:`instructions <swiftchat_bot_setup>` to set up one.


3. Clone the repo "Chatbot Starter Kit"
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
You may any framework to build your backend. To quick start, we've created a `Chatbot Starter Kit <https://github.com/MadgicalSwift/chatbot-starter-kit>`_. It has a sample code structure of a typical Bot application, which will help you to kick start without wasting time on setting up boilerplate code. Please follow the README given in repo to setup and run the code.

**Make Changes to the Starter Kit Code as per your Bot Configurations** 

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

4. Host the bot locally using ngrok
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
You can either publish this application on various cloud services like Heroku, Firebase, AWS, etc. or you can try NGRok which will create a reverse proxy for your locally hosted bot. Follow the instructions from the NGRok official website to generate a URL for your locally running bot application. Once the URL is generated, set this URL as a webhook URL on the Swiftchat dashboard of your bot.

Your bot is now ready, you can test it by visiting the bot URL and saying "hi". It'll print a welcome message as configured in the Chatbot Starter Kit. Now it's up to you, how you want to customize it.


