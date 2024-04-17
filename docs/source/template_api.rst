News Chatbot Template
======================

Welcome to our developer guide for crafting your custom news chatbot using our intuitive template! This document will lead you through the straightforward process of tailoring the template to your specifications and constructing your unique news chatbot. Let's dive in and begin building!

Prerequisites
-------------

Before you embark on this journey, ensure you have met the following requirements:

- Node.js and npm installed
- Nest.js CLI installed (npm install -g @nestjs/cli)
- Accessible MySQL database

Getting Started
---------------

Installation and Setup
~~~~~~~~~~~~~~~~~~~~~

Let's set up everything we need before diving into development:

1. **Clone the Repository:** Fork and clone the GitHub repository into your preferred IDE using `git clone "URL"`. Navigate to the working directory with `cd news-chatbot-template`.

2. **Install Dependencies:** `npm install`

3. **Update Environment Variables:** Rename the demo `.env.text` file to `.env` and fill in your configuration details such as API URLs, keys, and database credentials.

    ```
    API_URL = API_URL
    BOT_ID = BOT_ID
    API_KEY = API_KEY
    DATA_BASE = DATA_BASE
    DB_HOST = DB_HOST
    DB_USER = DB_USER
    DB_PASSWORD = DB_PASSWORD
    ```

Understanding the Flow
-----------------------

Before making any changes, let's grasp how the news template operates:

- Users are greeted with a message and presented with news categories upon initiating a conversation.
- After selecting a category, users are shown news stories and related sub-categories.
- Upon selecting a sub-category, more news is displayed with options to return to the main menu or explore other categories.

Making Modifications
---------------------

Now that the groundwork is laid, let's move on to development:

1. **Update Strings:** Open the cloned repository and navigate to the `i18n` folder. There you will find two files for English and Hindi strings. Open the English-localized file. Update the strings like the welcome message, language message, message for choosing the news category, and message for going back to the main menu, and browse other category strings.

2. **Update Buttons:** In the same file, you will find all the buttons we have. In the file, you get a variable "categoryButtons" where we have our main news category buttons. Add or update the buttons. You can add as many news category buttons as you want. Once you have updated or added a news category, you can also add sub-category buttons for each news item. For this, you need to create sub-category buttons with the main news category name. For example, if you have a "Sports" news category, the variable name for the sub-category will be "Sports.". Inside this variable, you can add your sub-category buttons.

3. **Update Categories:** If you've made changes or added new news categories or sub-categories, ensure to include their names and news IDs in the categories variable. Similarly, update the subcategory and category lists.

4. **Adjust Article Numbers:** Update the articleNumbers variable to specify the number of news stories per page and total stories.

Integrating Your News Source
-----------------------------

If you wish to use a different news source, follow these steps:

1. Modify the `sendNewsAsArticleCarousel` function in the newsFetching file within the KhabriMedia folder to fetch news information from your desired source.
2. Adjust parameters and remove undesired ones in the chatbot.service file accordingly.

Webhook URL Setup
------------------

Setting up the webhook URL is a crucial step in configuring your news chatbot. Here's a step-by-step guide to get you started smoothly:

1. **Sign up for Ngrok:** Begin by accessing this [URL](https://ngrok.com/) and creating an account on Ngrok. Follow the sign-up process diligently to acquire your authorization token.
2. **Configure Ngrok:** Open your terminal and input the command `ngrok config add-authtoken <TOKEN>`, replacing `<TOKEN>` with your authorization token. This step authorizes Ngrok to function properly.
3. Open a new terminal and run this command `ngrok http 3000`. This will generate a forwarding URL. Copy and save this.
4. Open Postman or any other API platform, generate a new PUT request and insert the API `https://v1-api.swiftchat.ai/api/bots/<bot-id>/webhook-url` into the URL field, ensuring to replace `<bot-id>` with your specific bot ID.
5. Add the Bearer API-Key in the authorization tab.
6. Add this to the body and send the request. By doing so, the webhook URL will be in the bot for sending and receiving responses. `{"webhook_url": "<Forwarding URL/newschatbot>"}`.

All Set!
---------

With the necessary changes implemented, dependencies installed, and webhook URL configured, we're ready to proceed. Let's get started!

Running the App
---------------

```bash
$ npm run start


