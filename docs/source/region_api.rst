Region
=======
The "Region" API allows developers to specify the geographical scope of their bot's operation and visibility. By defining countries, states, or cities, developers can ensure their bot is discoverable in specific locations via the Discover section. This feature enhances user engagement by making the bot accessible to users within specified regions based on their provided location in their profiles. Notably, if no region is selected, the bot remains searchable to all users within the country where it was registered, based on the registered mobile number's dial code.

1. Get all the countries and their codes, where you can develope your bot using this **GET** ``https://v1-api.swiftchat.ai/api/regions/countries`` API. Use any API platform and enter your API-key in the authorization tab and send the request.
   
   This will give you all countries with their code like this:

   .. code-block:: json
    {
    "data": [
        {
        "code": "IN",
        "name": "India"
        },
        {
        "code": "SG",
        "name": "Singapore"
        }
    ]
    }

----------------------------
    