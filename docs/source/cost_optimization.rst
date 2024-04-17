How to Optimise Open AI Cost?
==================================

OpenAI provides powerful natural language processing capabilities through its API services. However, the usage of these services can result in significant costs, especially in scenarios with high query volumes. To optimize costs without compromising functionality, the following strategies can be employed based on the features of the ChatBot system.

Caching
--------------------
In the caching mechanism, the system maintains a vector database to store pairs of questions and their corresponding answers. Each question is associated with its relevant answer.

- When a user asks a question, the system retrieves the vector representation of the question from the database.
- It then calculates the cosine similarity between the user's question vector and the question vectors stored in the database.
- Cosine similarity is a measure of similarity between two non-zero vectors in an inner product space. It measures the cosine of the angle between the vectors and ranges from -1 to 1. A value of 1 indicates perfect similarity, while -1 indicates perfect dissimilarity.

Let's say for example we have a question stored in our database with it's answer, and the user asks a similar question

.. code-block:: json

    Question in vector database: "What is the capital city of France?"
    Question asked by user: "Which city is the capital of France?"
        
-------------------

Using the cosine similarity formula, we compute the cosine similarity between Question 1 and Question 2.

After computing the cosine similarity value, we compare it to a predefined threshold. If the cosine similarity exceeds the threshold, we consider the questions to be sufficiently similar.

In this case, since the questions are asking for the same information but rephrased differently, the cosine similarity value is likely to be high, indicating a strong similarity between the questions. As a result, the system would recognize that both questions are essentially the same and retrieve the appropriate answer from the database.


Profanity check
----------------------

The profanity check feature is designed to filter out inappropriate or unaccepted language or words used by users when interacting with the bot.

- The system utilizes a list of predefined profane or inappropriate words and phrases.
- When a user submits a question or message, the system scans the text for the presence of any profane words or phrases.
- If any profanity is detected, the system responds with a regret message.

Sentence Length
^^^^^^^^^^^^^^^^^^^^^
Sentence length analysis is performed to determine the validity of user questions based on the number of words in the input. It helps filter out nonsensical or incomplete queries that may not provide enough context for the bot to generate a meaningful response.

- When a user submits a question, the system calculates the number of words in the input text.
- If the number of words exceeds a predefined threshold (e.g., 3 words), the system considers the question valid and proceeds with further processing.
- If the number of words is below the threshold, the system responds with a regret message indicating that the input is not a valid question.

Pool of Blacklist Words
^^^^^^^^^^^^^^^^^^^^^^^^^
The pool of blacklist words consists of terms or topics that are deemed irrelevant to the bot's domain or purpose. These words typically include names of songs, movies, celebrities, or other topics that are not related to the bot's area of expertise.

For example: the blacklist pool could be like this

['song', 'music', 'track', 'album', 'artist','djsong','video', 'clip', 'movie', 'film']

- The system maintains a list or array of blacklist words, which are predetermined based on the bot's domain and purpose.
- When a user submits a question, the system checks the input text for the presence of any blacklist words.
- If any blacklist words are detected, the system responds with a message indicating that the topic is not relevant to the bot's domain.

Benefits
^^^^^^^^
- The pool of blacklist words helps ensure that the bot stays focused on its intended purpose and provides relevant responses to user queries.
- Sentence length analysis ensures that the bot focuses on processing meaningful and complete questions, improving the quality of interactions with users.

Similarity cutoff
--------------------

The similarity cutoff feature filters out questions that meet basic criteria but aren't relevant to the bot's purpose. Instead of querying directly to OpenAI services, it checks if the question aligns with the bot's domain before proceeding.

- If the user's question passes the minimum word count and blacklist word checks, the system compares it with a set of predefined topics or keywords related to the bot's domain to check if the question is relevant to or not. For instance, if your bot is about religion and spirituality, questions about celebrities like "Who is Amitabh?" might not be relevant. 
- The system calculates a similarity score between the user's question and each predefined topic or keyword related to the bot's domain.
- A predefined similarity threshold is set to determine if the user's question is sufficiently related to the bot's domain.
- If the similarity score exceeds the threshold for any topic or keyword, the question is considered relevant and further processing may proceed. The system may then proceed to query external services like OpenAI to generate a response.
- If the similarity score falls below the threshold for all topics or keywords, the question is deemed unrelated, and further processing is halted. The system skips querying external services and directly responds with a regret message, informing the user that the question is unrelated to the bot's domain.


Rate limiting
----------------

Rate limiting restricts users to a certain number of questions for free. Once this limit is reached, users must pay for continued use of the service. This measure helps manage server load, prevent abuse, and potentially generate revenue from users who exceed the free limit.