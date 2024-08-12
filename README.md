# LawSikhoAssistant - Detailed README

## Description

**LawSikhoAssistant** is an advanced AI-powered chatbot designed to interact with users over WhatsApp. It provides users with comprehensive information about legal courses offered by LawSikho, helping them make informed decisions about their legal education. The chatbot leverages state-of-the-art technologies to facilitate smooth communication, efficient data management, and accurate responses.

## Features

- **Natural Language Processing (NLP):** Utilizes OpenAI's GPT-3.5-turbo model to understand and generate human-like responses based on user queries.
- **Database Integration:** Uses Firebase Firestore to store and retrieve document embeddings, enabling scalable and efficient data management.
- **Text Splitting:** Automatically processes large text files by splitting them into smaller, manageable chunks to facilitate easier analysis and querying.
- **WhatsApp Integration:** Communicates with users via WhatsApp, using the Twilio API to handle sending and receiving messages.
- **Customizable Prompt Templates:** Allows for the creation of dynamic response templates tailored to specific user interactions and contexts.
- **Chat History Management:** Maintains context-aware responses by keeping track of user interactions and conversation history.

### 1. Install Required Libraries

Ensure that Python is installed on your machine. Use pip to install the necessary libraries:

    pip install firebase-admin openai langchain flask twilio python-dotenv

- **firebase-admin:** For interacting with Firebase Firestore.
- **openai:** To utilize OpenAI's GPT-3.5-turbo model for natural language processing.
- **langchain:** Provides tools for text splitting, embeddings, and managing AI functions.
- **flask:** To create a web server for handling webhook requests from Twilio.
- **twilio:** Facilitates sending and receiving messages through WhatsApp.
- **python-dotenv:** Loads environment variables from a `.env` file.

### 2. Create a .env File

Create a file named `.env` in the root directory of your project. This file will store sensitive information such as API keys and credentials:

    OPENAI_API_KEY=your_openai_api_key
    TWILIO_ACCOUNT_SID=your_twilio_account_sid
    TWILIO_AUTH_TOKEN=your_twilio_auth_token
    TWILIO_WHATSAPP_NUMBER=your_twilio_whatsapp_number

Replace the placeholders with your actual API keys and credentials.

## Code Overview

### Web Scraping, Content Extraction, and Storing in Firestore

1. **Web Scraping and Content Extraction**
   - **`fetch_and_parse_url(url)`** retrieves and parses HTML content into a BeautifulSoup object. **`extract_headings_with_content(soup)`** organizes and extracts headings with their associated content. **`extract_specific_div_content(soup)`** retrieves text from `div` elements with the class `refundPolicy`. **`extract_urls(soup, base_url)`** collects and resolves URLs from anchor tags, and **`format_extracted_content(headings_content, div_content, urls)`** combines and formats this content into a structured output.

2. **Storing Chunks in Firestore**
   - **Initialize Firestore Client and Read Data File:** Sets up the Firestore client with credentials from a JSON file and reads the text data from a file.
   - **Process and Store Text Chunks:** Splits the text data into chunks using `RecursiveCharacterTextSplitter`, embeds them with OpenAI embeddings, and stores them in Firestore. Existing documents in the collection are not re-inserted.
   - **Subsequent Steps:** After storing, the system uses indexing methods to retrieve relevant chunks based on user queries, enabling accurate and contextually appropriate responses.




