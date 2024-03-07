Media
========

The "Media" API facilitates the management of media files used in bot communication. It allows developers to upload, delete, and retrieve URLs of media files from their repository. Supported media formats include images, videos, and possibly other multimedia formats, enhancing the variety and richness of content that bots can deliver to users.

1. Upload your media on the bot repository using this **POST** ``https://v1-api.swiftchat.ai/api/bots/<bot-id>/media`` API. You have to provide the file type and file path in the body section in the form-data format.
   
   .. image:: ../images/api_reference_images/upload_media.png
        :alt: login page 
        :width: 2500
        :height: 300
        :align: center
    
   On successful completion you will recieve the media-id.

   .. code-block:: json
    
    {
    "id": "WLnB4QQVC05vILF_BkKa2"
    }

-----------------------------


2. Delete the media when that's of no use using the **Delete** media api ``https://v1-api.swiftchat.ai/api/bots/<bot-id>/media/<media-id>``. Replace the bot-id and media-id in the api and send the request. You will get **OK** and **200** on successful completion.
3. Retrieve the media url that is used for communication between user and bot. The fetched url will be valid for 15 minutes only. 
   
   GET API: ``https://v1-api.swiftchat.ai/api/bots/<bot-id>/media/<media-id>``
