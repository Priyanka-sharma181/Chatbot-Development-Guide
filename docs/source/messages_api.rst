Messages
============

The SwiftChat Message API enables developers to interact with users through various message types, including text, documents, images, videos, audio, buttons, cards, and more. It supports initiating conversations with users using pre-approved templates after the 24-hour window following the last conversation initiation by either the user or the bot. Developers can send a wide range of messages, including interactive ones with buttons, action messages, and cards, enhancing user engagement and communication within the SwiftChat platform.


1. **Send Text Message:** If you want to send a simple text message to user like we sent "Hello World!", you can use this **POST** ``https://v1-api.swiftchat.ai/api/bots/<bot-id>/messages`` API. You need to provide your bot-id, to (phone number), type, text as a parameter.
   
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
   
   On successfully sending text message, in response it generates a message-id.

   .. code-block:: json

    {
      "id": "ba69108d-fed6-4573-be11-383a81a074bb"
    }
    
------------------------------

2. **Send Document Message By Media-Id:** Send a document message to user using the media-id of document with this **POST** ``https://v1-api.swiftchat.ai/api/bots/<bot-id>/messages``. Similar to text message it will generate a id for message. Have a look at below sample body.
   
   body:

   .. code-block:: json
    
    {
        "to": "<recepient-mobile>",
        "type": "document",
        "document": {
            "id": "<media-id>",
            "name": "<document-filename>",
            "body": "<document-caption>"
        },
        "rating_type": "thumb"
    }

--------------------------   

    Response:

    .. code-block:: json

        {
         "id": "6262514b-ef48-4d30-bb61-07bd80670e1b"
        }
-------------------------

3. **Send Document Message By Media-Url:** It has similar approach as above API. Instead of media-id we use Media-Url here with this **POST** ``https://v1-api.swiftchat.ai/api/bots/<bot-id>/messages``.
   
   Body:

   .. code-block:: json

    {
        "to": "<recepient-mobile>",
        "type": "document",
        "document": {
            "url": "<media-url>",
            "name": "<document-filename>",
            "body": "<document-caption>"
        },
        "rating_type": "thumb"
    }

------------------------

4. **Send Image Message:**
   
   1. **By Media-Id:** This **POST** ``https://v1-api.swiftchat.ai/api/bots/<bot-id>/messages`` API sends the image to the user by the media ID of the image. The supported image types are JPEG, PNG, and GIF.
      
      Body:

      .. code-block:: json

        {
            "to": "<recepient-mobile>",
            "type": "image",
            "image": {
                "id": "<media-id>",
                "body": "<image-caption>"
            },
            "rating_type": "thumb"
        }
-------------------

   2. **By Media-Url:** This **POST** ``https://v1-api.swiftchat.ai/api/bots/<bot-id>/messages`` API sends the image to the user by the media url of the image. The supported image types are JPEG, PNG, and GIF.
      
       Body:

       .. code-block:: json

        {
            "to": "<recepient-mobile>",
            "type": "image",
            "image": {
                "url": "<media-url>",
                "body": "<image-caption>"
            },
            "rating_type": "thumb"
        }
            
----------------------------

   Response:

    .. code-block:: json

        {
            "id": "c7d38219-3667-4f2f-bdf2-9428f17dd602"
        }
    
----------------------------   

5. **Send Video Message:**

   1. **By media-id:** This **POST** ``https://v1-api.swiftchat.ai/api/bots/<bot-id>/messages`` API sends the video to the user by the media ID of the video. The supported video types are MP4 and 3GP.
       
       Body:

       .. code-block:: json

        {
            "to": "<recepient-mobile>",
            "type": "video",
            "video": {
                "id": "<media-id>",
                "title": "<video-title>"
            },
            "rating_type": "thumb"
        }
----------------------------------------

   2. **By Media-Url:** This **POST** ``https://v1-api.swiftchat.ai/api/bots/<bot-id>/messages`` API sends the video to the user by the media url of the video. The supported video types are MP4 and 3GP.
    
       Body:

       .. code-block:: json

        {
            "to": "<recepient-mobile>",
            "type": "video",
            "video": {
                "id": "<media-id>",
                "title": "<video-title>"
            },
            "rating_type": "thumb"
        }
---------------------------------------

       
   Response:

        .. code-block:: json

            {
              "id": "a912a4fa-9833-4ba6-86a0-ed8557bb5bc9"
            }
---------------------------------
                    
6. **Send Audio Message:** 
   
    1. **By Media-Id:** We can send the audio to user using the audio-id of audio using this **POST** ``https://v1-api.swiftchat.ai/api/bots/<bot-id>/messages`` API.
       
       Body:
       
       .. code-block:: json

        {
            "to": "<recepient-mobile>",
            "type": "audio",
            "audio": {
                "id": "<media-id>",
                "title": "<audio-title>",
                "body": "<audio-caption>"
            },
            "rating_type": "thumb"
        }
------------------------------

   2. **BY Media-Url:** We can send the audio to user using the audio-url of audio using this **POST** ``https://v1-api.swiftchat.ai/api/bots/<bot-id>/messages`` API.
       
        Body:

        .. code-block:: json

            {
                "to": "<recepient-mobile>",
                "type": "audio",
                "audio": {
                    "url": "<media-url>",
                    "title": "<audio-title>",
                    "body": "<audio-caption>"
                },
                "rating_type": "thumb"
            }

 -------------------------------------

   Response:

        .. code-block:: json
               
            {
                "id": "b0e448d2-abf1-48bf-b536-2794d3c6ad25"
            }
----------------------------- 


7. **Send Button Message:** Use this **POST** ``https://v1-api.swiftchat.ai/api/bots/<bot-id>/messages`` API to create and send buttons to user. You need to provide parameters like to, type, button etc. On successfully sending buttons it will generate the id.
   
   Body:

   .. code-block:: json

        {
        "to": "<recepient-mobile>",
        "type": "button",
        "button": {
            "body": {
                "type": "text",
                "text": {
                    "body": "<message-text>"
                }
            },
            "buttons": [
                {
                    "icon": "<button-icon>",
                    "type": "<button-type>",
                    "body": "<button-text>",
                    "reply": "<user-click-response>"
                },
                {
                    "icon": "<button-icon>",
                    "type": "<button-type>",
                    "body": "<button-text>",
                    "reply": "<user-click-response>"
                }
            ],
            "allow_custom_response": false
        },
        "rating_type": "thumb"
        }
        
--------------------------------------------

8. **Send Multi Select Button:** If you want to create buttons where user can select multiple options, you can create buttons using this **POST** ``https://v1-api.swiftchat.ai/api/bots/<bot-id>/messages`` API.
   
   Body:

   .. code-block:: json

    {
        "to": "<recepient-mobile>",
        "type": "button",
        "multi_select_button": {
            "body": {
                "type": "text",
                "text": {
                    "body": "<message-text>"
                }
            },
            "multi_select_button": [
                {
                    "icon": "<button-icon>",
                    "type": "<button-type>",
                    "body": "<button-text>",
                    "reply": "<user-click-response>"
                },
                {
                    "icon": "<button-icon>",
                    "type": "<button-type>",
                    "body": "<button-text>",
                    "reply": "<user-click-response>"
                }
            ],
            "allow_custom_response": false
        },
        "rating_type": "thumb"
    }

-----------------------------------