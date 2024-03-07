Messages
============

The SwiftChat Message API enables developers to interact with users through various message types, including text, documents, images, videos, audio, buttons, cards, and more. It supports initiating conversations with users using pre-approved templates after the 24-hour window following the last conversation initiation by either the user or the bot. Developers can send a wide range of messages, including interactive ones with buttons, action messages, and cards, enhancing user engagement and communication within the SwiftChat platform.


1. Send Text Message: If you want to send a simple text message to user like we sent "Hello World!", you can use this **POST** ``https://v1-api.swiftchat.ai/api/bots/<bot-id>/messages`` API. You need to provide your bot-id, to (phone number), type, text as a parameter.
   
   Example body:

   .. code-block:: json

    {
        "to": "{{Recepient-Mobile}}",
        "type": "text",
        "text": {
            "body": "<message-text>"
        },
        "rating_type": "thumb"
    }
    
--------------------------
   