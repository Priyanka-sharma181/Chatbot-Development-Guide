Creating Your First Chatbot
====================
To begin utilizing the starter kit, you'll need to obtain a Chatbot ID. You can create a chatbot either manually or via API.

Creating a Bot Using the SwiftChat API
------------------------
------------------------
The SwiftChat APIs act as the conduit between your chatbot and yourself, processing your data accordingly. 

You can employ any tool or platform to interact with the SwiftChat APIs. In this instance, we'll demonstrate using **Postman**.

Steps
^^^^^^^^^^

1. Open `SwiftChat APIs Documentation <https://documenter.getpostman.com/view/20587790/UyrGCuhH#intro>`_
2. Click on **Run In Postman**. This will provide you with two options: **Postman for web** and **Postman for ubuntu**.

.. image:: run_in_postman.jpg
   :alt: Deployment Structure
   :width: 1850
   :height: 400
   :align: center

3. Click on **Postman for web**. You'll be redirected to a page where you can choose your Postman account. Sign in to your account and proceed with the login process.
4. After logging in, you'll be presented with a page where you need to select a workspace to save the SwiftChat APIs.

.. image:: collection.png
   :alt: Deployment Structure
   :width: 1300
   :height: 400
   :align: center


5. The SwiftChat APIs collection will now be saved in your chosen workspace. Within the **Bot** folder, you'll find the **create bot** API request. Select this request and input details such as the Bot name and your number in the **Body** section.

.. note::
    Make sure you have updated the API key in the environment variable

.. image:: bot_body.png
   :alt: Deployment Structure
   :width: 1300
   :height: 300
   :align: center

6. On successfully creating bot you will receive a message **created** and status code **OK**

.. image:: successful_bot.png
   :alt: Deployment Structure
   :width: 1300
   :height: 100
   :align: center

7. After creating bot, use the **varify API** and varify your bot. This will generate the bot ID.

Creating a Bot Using the SwiftChat Dashboard
------------------------
You can also create bot using your SwiftChat Merchant Dashboard

Steps
1. Login to your `SwiftChat Merchant Dashboard <https://dashboard.swiftchat.ai/bots>`_.
2. Click on **Add New Bot** button.

.. image:: add_bot.png
   :alt: Deployment Structure
   :width: 1000
   :height: 100
   :align: center

Clicking this button will redirect you to a page where you can input the bot details, including the phone number, bot name, and bot type. Fill these details 

.. image:: bot_detail.png
   :alt: Deployment Structure
   :width: 1300
   :height: 500
   :align: center
