Conversation
==============

This API helps you find out how many conversations took place between a bot and users within a specific time range. For instance, if a conversation started at 5:30 AM UTC and ended at 5:29 AM UTC the following day, it would be counted in that range. The API tracks dates and times using UTC format (Coordinated Universal Time), and you can specify the date range you're interested in using the format YYYY-MM-DD.

GET API: ``https://v1-api.swiftchat.ai/api/billing/bots/<bot-id>/conversations?start_date=<start-date>&end_date=<end-date>``

Provide the bot-id, start-date and end-date in the API and send the request. This will generate the conversation count initiated by bot or user between the start_date and end_date.

Response:

.. code-block:: json

    {
        "data": [
            {
            "conversation_start_date": "2022-04-19",
            "user_initiated_conversations": 15,
            "business_initiated_conversations": 2
            },
            {
            "conversation_start_date": "2022-04-26",
            "user_initiated_conversations": 12,
            "business_initiated_conversations": 8
            },
            {
            "conversation_start_date": "2022-04-28",
            "user_initiated_conversations": 11,
            "business_initiated_conversations": 4
            },
            {
            "conversation_start_date": "2022-05-03",
            "user_initiated_conversations": 3,
            "business_initiated_conversations": 10
            }
        ]
    }

-------------------------------------