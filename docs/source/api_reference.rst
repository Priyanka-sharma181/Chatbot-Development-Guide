SwiftChat APIs
====================
SwiftChat platform allows you to connect with a large number of users effortlessly, without them needing to download an extra app.

SwiftChat APIs helps you integrate your interactive bots with SwiftChat, so you can easily manage them and chat with users using text, pictures, or interactive messages like buttons.

Merchant
------------------------
Use this API to sign up, login, retrieve, and generate API keys for managing your merchant account on Swiftchat's merchant platform. 

1. Create account using Post ``https://v1-api.swiftchat.ai/api/merchants`` API. Provide the required information including Name, Email, and Password in the request body.

.. code-block:: json

    {   
    "name": "<merchant-name>",
    "email": "<merchant-email>",
    "password": "<merchant-password>"
    }
-----------------   

Submit the required details and send the POST request. Upon successfully creating an account, you will receive your merchant ID.

.. code-block:: json

    {
    "id": "01xxxxxxxxxxxx"
    }
-----------------

2. 