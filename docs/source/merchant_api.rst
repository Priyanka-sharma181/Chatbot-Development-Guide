Merchant
------------------------
Use this APIs to sign up, login, retrieve, and generate API keys for managing your merchant account on Swiftchat's merchant platform. 

1. Create account using **POST** ``https://v1-api.swiftchat.ai/api/merchants`` API. Provide the required information including Name, Email, and Password in the request body.

.. code-block:: json

    {   
    "name": "<merchant-name>",
    "email": "<merchant-email>",
    "password": "<merchant-password>"
    }
-----------------   

Submit the required details and send the **POST** request. Upon successfully creating an account, you will receive your merchant ID.

.. code-block:: json

    {
    "id": "01xxxxxxxxxxxx"
    }
-----------------

2. To retrieve your merchant details, utilize the following **GET** API endpoint: ``https://v1-api.swiftchat.ai/api/merchants/<merchant-id>`` and enter your merchant ID in it..  This API provides information such as ID, name, email, email verification status, creation date, etc.
   
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
   
   - **Generate OTP:** To verify your account, generate the OTP by sending a **POST** request to ``https://v1-api.swiftchat.ai/api/merchants/<merchant-id>/api-key/otp`` API endpoint with the merchant ID. This will send the OTP to your email.
   - **Varify OTP:** Use this API **POST** ``https://v1-api.swiftchat.ai/api/merchants/<merchant-id>/api-key/otp/verify`` for email varification. 

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

   - **Generate API key:** To generate the API Key use this **POST** ``https://v1-api.swiftchat.ai/api/merchants/<merchant-id>/api-key/generate`` API with the merchant-id. Provide the token that generated in **varify OTP** API, in the body.
    
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
