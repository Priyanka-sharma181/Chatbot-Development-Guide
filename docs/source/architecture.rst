Chatbot Architecture
=====

This document guides you through the development of a chatbot solution that can be published on the Swiftchat Platform. A typical chatbot solution comprises the following components:

- **Chat Interface:** Swiftchat
- **Chatbot Backend:** Responsible for managing user interactions within the Swiftchat Platform
- **AI Query Engine:** Processes user queries using natural language processing techniques
- **Database:** Stores user data, manages knowledge, and maintains chat history and logs

Deployment Architecture
~~~~~~~~~~~~~~~~~~~~~~~
![](image.png)

Chatbot Backend
----------------

The Chatbot Backend is the primary application that handles user interactions with the Swiftchat Platform. Its major responsibilities include:

- Handling logic for various use cases
- Calling Swiftchat APIs to interact with users
- Utilizing NLP Backend services for processing user queries in natural language.
- Managing user preference data, chat history

This backend is sufficient for Rule-Based bots where no natural language processing is required.

NLP Backend Services
---------------------

This module handles natural language queries using generative AI technologies such as OpenAI or open source LLMs. It should handle the following typical services:

- Ingesting and managing knowledge into the Vector database
- Generating answers for queries asked in natural language using LLM services such as OpenAI or other LLMs
- Caching results to optimize LLM service cost

Vector Database
---------------

The Vector Database stores text embeddings (vectors) that can be retrieved based on semantic similarity. Utilize the Vector database to store:

- Documents such as PDFs, text files, text strings, etc., as knowledge on which your bot will answer.
- Cache results from OpenAI or other LLM services

Logging, Health Check, Data Analytics
--------------------------------------

Using AWS CloudWatch, you can monitor the health of your infrastructure, including server logs, resource utilization, etc.

Set up an Alarm service to receive alerts for unprecedented issues. Typical things to monitor include:

- EC2 Instances Utilization
- Number of Requests

Todos
~~~~~

- Migrate from RDS to DynamoDB
- Add Gateway endpoint (to reduce latency)
- Migrate from NLB to ALB
- Integrate Bots (Ramayan and BG Bots)
- Implement General AI (Gen AI) for Ramayan
- Implement Weaviae

