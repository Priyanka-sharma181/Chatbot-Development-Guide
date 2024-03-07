Region
=======
The "Region" API allows developers to specify the geographical scope of their bot's operation and visibility. By defining countries, states, or cities, developers can ensure their bot is discoverable in specific locations via the Discover section. This feature enhances user engagement by making the bot accessible to users within specified regions based on their provided location in their profiles. Notably, if no region is selected, the bot remains searchable to all users within the country where it was registered, based on the registered mobile number's dial code.

1. Retrieve the available list of countries and their codes in which you can make your bot searchable using this **GET** ``https://v1-api.swiftchat.ai/api/regions/countries`` API. Use any API platform and enter your API-key in the authorization tab and send the request.
   
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

2. Retrieve the available list of states in a country and their codes in which you can make your bot searchable using this **GET** ``https://v1-api.swiftchat.ai/api/regions/states?country_code=IN``. Replace the country code with your own one.
   
   Get a response like this:

   .. code-block:: json

        {
        "data": [
            {
            "code": "AN",
            "name": "Andaman and Nicobar Islands"
            },
            {
            "code": "AP",
            "name": "Andhra Pradesh"
            }
        ]
        }
   
----------------------------

3. If you want to make your bot searchable in particular cities, you can use this **GET** ``https://v1-api.swiftchat.ai/api/regions/cities?country_code=IN&state_code=UP`` api to retrieve all cities where you can make your bot searchable. Replace the state code with you own one.
   
   You will get response like this:

   .. code-block:: json
        
    {
        "data": [
            "Achhnera",
            "Afzalgarh",
            "Agra",
            "Āgra",
            "Ahraura",
            "Ajodhya",
            "Akbarpur",
            "Alīganj",
        ]
    }
        
--------------------------

4. Get all the countries where your bot is active and operational by using this **GET** ``https://v1-api.swiftchat.ai/api/bots/<bot-id>/availability/regions`` API. Replace the bot-id with your bot-id.
   
   Response:

   .. code-block:: json
            
        {
        "data": [
            {
            "country_code": "IN",
            "states": [
                "AP"
            ],
            "cities": [
                {
                "state_code": "AP",
                "cities": [
                    "Attili",
                    "Avanigadda"
                ]
                }
            ]
            },
            {
            "country_code": "SG",
            "states": [],
            "cities": []
            }
        ]
        }
   
---------------------------------   

5. If you want to make your bot available in a particular country use this **PUT** ``https://v1-api.swiftchat.ai/api/bots/<bot-id>/availability/regions`` API. On successful update you will get status code **200** and **OK**.