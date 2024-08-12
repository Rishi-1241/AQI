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

## Code Overview

### Web Scraping and Content Extraction

1. **`fetch_and_parse_url(url)`** and **`extract_headings_with_content(soup)`**
   - **Overview:** `fetch_and_parse_url(url)` retrieves and parses HTML content from the specified URL into a BeautifulSoup object. `extract_headings_with_content(soup)` then organizes and extracts headings along with their associated content, such as paragraphs and lists.

2. **`extract_specific_div_content(soup)`**, **`extract_urls(soup, base_url)`**, and **`format_extracted_content(headings_content, div_content, urls)`**
   - **Overview:** `extract_specific_div_content(soup)` retrieves text from `div` elements with the class `refundPolicy`. `extract_urls(soup, base_url)` collects and resolves URLs from anchor tags, while `format_extracted_content(headings_content, div_content, urls)` combines and formats the extracted content into a structured output.

## Usage

1. **Install Required Libraries:**
   - Ensure you have the `requests` and `beautifulsoup4` libraries installed. You can install them using pip:
     ```bash
     pip install requests beautifulsoup4
     ```

2. **Run the Script:**
   - Execute the script to fetch, process, and save content from the specified URL. The output will be saved in `deepsolve.txt`.
