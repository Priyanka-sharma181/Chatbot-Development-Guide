.. _swiftchat_bot_setup:
Setting Up a New Bot
====================
To begin utilizing the starter kit, you'll need to obtain a bot ID. You can create a chatbot either manually or via API.

Creating a Bot Using the SwiftChat API
------------------------
------------------------
The SwiftChat APIs act as the conduit between your chatbot and yourself, processing your data accordingly. 

You can employ any tool or platform to interact with the SwiftChat APIs. In this instance, we'll demonstrate using **curl**.

**Steps**

1. Open your terminal or command prompt. If you don't have curl installed, you can install it using npm by running the ``npm install -g curl`` command in your terminal
2. Create a new **POST** request using curl
3. Use the following API endpoint:``https://v1-api.swiftchat.ai/api/bots`` 
4. Include your API key in the header that you obtained during `Obtaining API Key <get_api_key.html>`_. and add the header to your curl request
5. In the body, include details such as bot-name, mobile-number, and bot-category::
 
      curl --location 'https://v1-api.swiftchat.ai/api/bots' \
       --header "Content-Type: application/json" \
       --header "Authorization: Bearer YOUR_API_KEY_HERE" \
       --data '{
           "mobile": "+91XXXXXXXXXX",
           "configuration": {
           "name": "Test"
           "category":"Education"
          }
      }'

6. On successfully creating bot you will receive a message indicating **created**.

7. After creating bot, use the `**varify API** <https://documenter.getpostman.com/view/20587790/UyrGCuhH#a5fa0876-d1b1-48de-a475-dad2ff467071>`_  to generate the bot ID.


Creating a Bot Using the SwiftChat Dashboard
------------------------
You can also create bot using your SwiftChat Merchant Dashboard

**Steps:**

1. Login to your `SwiftChat Merchant Dashboard <https://dashboard.swiftchat.ai/bots>`_.
   

.. tip:: 

   - Create your merchant account using this Post `API <https://documenter.getpostman.com/view/20587790/UyrGCuhH#57d73550-1c15-41a5-ac7e-0ba20b60b3e4>`_ 
   - Complete business KYC and email varification

2. Click on **Add New Bot** button.

.. image:: ../images/create_bot_images/add_bot.png
   :alt: Deployment Structure
   :width: 1000
   :height: 100
   :align: center


3. Clicking **Add New Bot** button will redirect you to a page where you can input the bot details, including the phone number, bot name, and bot type.Enter these details and proceed for verification. Once verification is completed, the bot will be created and activated.

.. image:: ../images/create_bot_images/bot_detail.png
   :alt: Deployment Structure
   :width: 1300
   :height: 500
   :align: center


4. Copy the bot link and save it for future reference. The link should resemble this format::

       https://cgweb.page.link/?link=https%3A%2F%2Fweb.convegenius.ai%3FbotId%3D0216260609726241&apn=ai.convegenius.app

   - In the link, the bot ID is structured as **botId%3D0216260609726241**, where the actual ID follows the "3D" prefix. So here the ID is **0216260609726241**.


