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

Similarity cutoff
--------------------

Rate limiting
----------------