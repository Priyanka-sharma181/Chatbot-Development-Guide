User Interaction
===========

In this guide, we'll walk you through using and customizing the starter kit code to build your own Chatbot. You'll learn about the structure of the starter kit, enabling you to make updates and manage user interactions effectively.

.. tip::
    First read about starter kit structure `here <repo_structure.html>`_

**Scenario:**

Let's start with a simple example. Suppose that when a user sends "hi", you want to display a greeting message along with two buttons for selecting their preferred language. When the user selects a language button, the language should change accordingly.

1. Present two buttons for language selection along with welcome message when user sends "hi"
2. Show a message for language change confirmation.
   

Implementation
------------------

Creating Buttons
^^^^^^^^^^^^^^^^

We'll begin by creating a new function in the chatbot.service file called createButtons. This function will utilize the SwiftChat POST send API to generate and send buttons to the user.

   .. code-block:: nest

          private async createButtons(from: string): Promise<void> {
            const url = `${this.apiUrl}/${this.botId}/messages`;
            const messageData = {
            to: from,
            type: 'button',
            button: {
                body: {
                type: 'text',
                text: {
                    body: choose language'
                },
                },
                buttons: [
                {
                    type: 'solid',
                    body: 'Hindi',
                    reply: 'Hindi',
                },
                {
                    type: 'solid',
                    body: 'English',
                    reply: 'English',
                },
                ],
                allow_custom_response: false,
            },
            };
            try {
            const response = await axios.post(url, messageData, {
                headers: {
                Authorization: `Bearer ${this.apiKey}`,
                'Content-Type': 'application/json',
                },
            });
            return response.data;
            } 
            catch (error) {
            console.error('errors:', error);
            }
        }

----------------------------------------            
        
**What This Code Snippets Will Do?**

- This method `createButtons` is a private asynchronous function used to create buttons for language selection in a chatbot.
- It takes the user's identifier (`from`) as a parameter to send the buttons to the correct recipient.
- The function constructs a URL using the API ``https://v1-api.swiftchat.ai/api/bots/<bot-id>/messages`` to specify the endpoint for sending messages.
- It prepares the message data, including the recipient (`to`), message type (`type`), and button details.
- The button message body contains a text prompt for the user to choose a language.
- Two buttons are provided for language selection: "Hindi" and "English".
- Each button has a solid style (`type: 'solid'`) and a corresponding reply value indicating the selected language (`reply: 'Hindi'` or `reply: 'English'`).
- The `allow_custom_response` property is set to `false` to restrict users from entering custom responses instead of selecting from the provided buttons.
- The function sends a POST request to the specified URL with the message data, including the user's authorization token (`Authorization: Bearer ${this.apiKey}`) and the content type (`'Content-Type': 'application/json'`).
- If the request is successful, it returns the response data; otherwise, it catches any errors and logs them to the console.
  

Now that we have created buttons, we have to show these buttons when the user sends "hi". Navigate to ``processMessage`` function and add a new const variable button_response in the body variable.
   
   .. image:: ../images/other_images/button_response_body.png
        :alt: Deployment Structure
        :width: 500
        :height: 100
        :align: left  


--------------------------------


Updating Message Processing
^^^^^^^^^^^^^^^^^^^^^^

Next, we'll update the processMessage function to handle user interactions. When the user sends "hi", we'll call both the sendWelcomeMessage and createButtons functions.
   
   .. code-block:: nest

        if (intent === 'greeting') {
            this.message.sendWelcomeMessage(from, userData.language);
        } 
    
------------------------------
    
    Replace this code block with below code

    .. code-block:: nest

        if (body.text.body === 'greeting') {
            this.message.sendWelcomeMessage(from, userData.language);
            await this.createButtons(from);
        } 
    
------------------------------


Handling Button Interaction
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Finally, we'll create a new condition to handle button interactions. If the button_response is true and there's a valid message body, we'll send a message confirming the language change.
   
The ``sendLanguageChangedMessage`` function takes the selected language as a parameter. It then retrieves the change_language_message from localized strings and sends the language change message according to the selected language.


   .. code-block:: nest

    else if (button_response && body.text){
        this.message.sendLanguageChangedMessage(from, button_response.body);
    }

-----------------------------------
   
By following these steps, you'll be able to change the user's language and customize the starter kit for your own bot.



NLP
============
In the above guide, we saw how to customize the starter kit to create our own bot and handle user interaction. Let's assume you have to design a chatbot that that takes the user input or query and provides the answers for their query. This is where the NLP becomes important.

NLP, or Natural Language Processing, is a branch of artificial intelligence (AI) focused on enabling computers to understand, interpret, and generate human language in a way that is both meaningful and useful. It involves the interaction between computers and humans through natural language.

NLP encompasses a range of tasks and techniques, including:

1. Text Processing: Breaking down text into its constituent parts, such as words, sentences, and paragraphs.
2. Tokenization: Splitting text into smaller units, or tokens, such as words or phrases.
3. Part-of-Speech Tagging: Assigning grammatical categories (e.g., noun, verb, adjective) to words in a sentence.
4. Named Entity Recognition (NER): Identifying and categorizing named entities (e.g., names of people, organizations, locations) in text.
5. Sentiment Analysis: Determining the sentiment or opinion expressed in a piece of text, such as positive, negative, or neutral.
6. Machine Translation: Translating text from one language to another automatically.
7. Question Answering: Generating answers to questions posed in natural language.

Overall, NLP enables computers to process, analyze, and understand human language, which has applications in various fields, including virtual assistants, chatbots, information retrieval, and language translation.

Top NLPs
-----------------

We have a list of top NLP that you can utilize in your chatbot. Some popular natural language processing (NLP) libraries and frameworks include:

1. NLTK (Natural Language Toolkit)
2. spaCy
3. Stanford NLP
4. Gensim
5. TextBlob
6. CoreNLP
7. OpenNLP
8. FastText
9. Transformers (such as BERT, GPT, etc.)
10. AllenNLP

These libraries offer various functionalities for tasks like tokenization, part-of-speech tagging, named entity recognition, sentiment analysis, and more.