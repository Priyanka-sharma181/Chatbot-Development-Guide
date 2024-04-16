Chatbot Template Developer Guide
==============

Welcome to our developer guide for crafting your custom news chatbot using our intuitive template! This document will lead you through the straightforward process of tailoring the template to your specifications and constructing your unique news chatbot. Let's dive in and begin building!

## Prerequisites

Before you embark on this journey, ensure you have met the following requirements:

- Node.js and npm installed
- Nest.js CLI installed (`npm install -g @nestjs/cli`)
- Accessible MySQL database

## Getting Started

### Installation and Setup

Let's set up everything we need before diving into development:

1. **Clone the Repository:** Fork and clone the GitHub repository into your preferred IDE using `git clone "URL"`. Navigate to the working directory with `cd news-chatbot-template`.

2. **Install Dependencies:** `npm install`

3. **Update Environment Variables:** Rename the demo `.env.text` file to `.env` and fill in your configuration details such as API URLs, keys, and database credentials.

```dotenv
API_URL = API_URL
BOT_ID = BOT_ID
API_KEY = API_KEY
DATA_BASE=DATA_BASE
DB_HOST=DB_HOST
DB_USER=DB_USER
DB_PASSWORD=DB_PASSWORD