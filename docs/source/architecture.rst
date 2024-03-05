Chatbot Architecture
=====
This document guides you through the development of a chatbot solution that can be published on the Swiftchat Platform. A typical chatbot solution comprises the following components:

- **Chat Interface:** Swiftchat
- **Chatbot Backend:** Responsible for managing user interactions within the Swiftchat Platform
- **AI Query Engine:** Processes user queries using natural language processing techniques
- **Database:** Stores user data, manages knowledge, and maintains chat history and logs

Deployment Architecture
~~~~~~~~~~~~~~~~~~~~~~~
.. image:: ../images/deployement_images/image.png
   :alt: Deployment Structure
   :width: 500
   :height: 500
   :align: center


Chatbot Backend
----------------
The Chatbot Backend serves as the core application responsible for managing user interactions on the Swiftchat Platform. Its key responsibilities include:

- Implementing logic for various use cases
- Utilizing Swiftchat APIs to engage with users
- Leveraging NLP Backend services for natural language query processing
- Managing user preferences and chat history

This backend suffices for Rule-Based bots where natural language processing is unnecessary.

NLP Backend Services
---------------------
This module handles natural language queries using generative AI technologies such as OpenAI or open-source LLMs. Its typical services include:

- Ingesting and managing knowledge within the Vector database
- Generating responses to queries posed in natural language using LLM services like OpenAI
- Caching results to optimize LLM service costs

Vector Database
---------------

The Vector Database stores text embeddings (vectors) retrievable based on semantic similarity. It is used to store:

- Documents such as PDFs, text files, and strings, serving as knowledge for bot responses
- Cache results from OpenAI or other LLM services

Logging, Health Check, Data Analytics
--------------------------------------

AWS CloudWatch facilitates monitoring infrastructure health, including server logs and resource utilization.

An Alarm service can be set up to receive alerts for unexpected issues. Key metrics to monitor include:

- EC2 Instances Utilization
- Request Counts

