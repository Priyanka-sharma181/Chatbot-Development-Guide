SwiftChat APIs
====================
SwiftChat platform allows you to connect with a large number of users effortlessly, without them needing to download an extra app.

SwiftChat APIs helps you integrate your interactive bots with SwiftChat, so you can easily manage them and chat with users using text, pictures, or interactive messages like buttons.

Merchant
------------------------
Use this APIs to sign up, login, retrieve, and generate API keys for managing your merchant account on Swiftchat's merchant platform. 

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

2. To retrieve your merchant details, utilize the following GET API endpoint: ``https://v1-api.swiftchat.ai/api/merchants/<merchant-id>`` and enter your merchant ID in it..  This API provides information such as ID, name, email, email verification status, creation date, etc.
   
   Response:

   .. code-block:: json

    {
    "merchant_id": "01xxxxxxxxxxxxxx",
    "name": "Test Merchant",
    "email": "test.merchant@test.com",
    "email_verified": 1,
    "status": "ACTIVE",
    "status_reason": null,
    "created_at": "2022-03-17T13:00:05.000Z"
    }
-----------------


3. If you want to generate a new API key, first generate the API-OTP and then verify your email using the generated OTP.
   
   - **Generate OTP:** To verify your account, generate the OTP by sending a POST request to ``https://v1-api.swiftchat.ai/api/merchants/<merchant-id>/api-key/otp`` API endpoint with the merchant ID. This will send the OTP to your email.
   - **Varify OTP:** Use this API ``https://v1-api.swiftchat.ai/api/merchants/<merchant-id>/api-key/otp/verify`` for email varification. 

    Body:

    .. code-block:: json

            {
            "otp": "<api-key-otp>"
            }
    -----------------

    Response

    .. code-block:: json

            {
            "token": "Fg-MTCepsbOmYMrAKikYq"
            }
    -----------------

   - **Generate API key:** To generate the API Key use this Post ``https://v1-api.swiftchat.ai/api/merchants/<merchant-id>/api-key/generate`` API with the merchant-id. Provide the token that generated in **varify OTP** API, in the body.
    
    Body:

    .. code-block:: json

        {
        "token": "<token>"
        }
    -----------------

    Response

    .. code-block:: json

        {
        "api_key": "bd4736fb-a478-4902-945f-86ab2t098g65"
        }
    -----------------

Bots
------------------------
Bot APIs serve multiple purposes, including creating, verifying, and retrieving bots. Additionally, they facilitate communication with the bot through messages, welcome banners, and more.

1. **Create Bot:** Want to create a new bot? Then use this Post ``https://v1-api.swiftchat.ai/api/bots`` API. Ensure to include parameters like mobile number and configuration details such as name and category.

.. code-block:: json

    {
    "mobile": "<bot-mobile-number>",
    "configuration": {
        "name": "<bot-name>",
        "category": "<category of the bot>"
    }
    }
------------------------

Upon successful creation of the bot, you will receive a 201 status code along with a message **Created**.

2. **Varify Bot:** This API is utilized to verify the mobile number associated with your newly created bot. To varify your bot you need to provide mobile number and the OTP that you received in the body.
   
   Body:

   .. code-block:: json

    {
    "mobile": "<bot-mobile-number>",
    "otp": "<otp>"
    }

------------------------

On successfull varification you will receive the bot ID.

    Response:

    .. code-block:: json

        {
        "id": "0295758414350769"
        }
    
------------------------    

3. If you want to gather information about all the bots linked to your merchant-id, you can use the Get API endpoint: ``https://v1-api.swiftchat.ai/api/merchants/<merchant-id>/bots``. Simply provide your merchant-id along with the API. This API will retrieve details such as the name, id, and phone number of all your bots.
   
   Response:

   .. code-block:: json

    {
    "data": [
    {
      "name": "Test Bot",
      "bot_id": "0295758414350769",
      "mobile": "+91XXXXXXXXXX"
    },
    {
      "name": "Test Bot 2",
      "bot_id": "0221741349325852",
      "mobile": "+91XXXXXXXXXX"
    }
    ]
    }
   
------------------------    

4. To collect all the information about a specific bot, utilize the following API: ``https://v1-api.swiftchat.ai/api/bots/<bot-id>/configuration``, inserting your bot's id. This will help you get information such has bot name, id, welcome message, buttons, photo, banner and more.
   
   Response

   .. image:: get_config_bot.jpg
   :alt: Deployment Structure
   :width: 1300
   :height: 400
   :align: center
