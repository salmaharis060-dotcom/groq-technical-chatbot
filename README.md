# Technical Q&A Chatbot

<img width="908" height="296" alt="image" src="https://github.com/user-attachments/assets/bffd68f0-31f6-4326-aea6-224e040e58ba" />

A command-line chatbot built with the Groq API that streams answers token by token and only answers technical questions.

## Features

- Streaming responses
- Keeps conversation history, so follow-up questions work
- A system prompt restricts answers to programming, IT, networking, cybersecurity, data and AI/ML
- Off-topic questions get a fixed refusal message
- If a request fails, it is removed from the history so you can retry
- API key is loaded from a `.env` file, never hardcoded

## Run it

1. Install the dependencies:
   ```
   pip install -r requirements.txt
   ```
2. Create a `.env` file in the project folder:
   ```
   GROQ_API_KEY=your_key_here
   ```
   You can get a free key from the Groq console.
3. Start the chatbot:
   ```
   python chatbot.py
   ```
4. Type `quit`, `exit` or `stop` to leave.

## Model

`openai/gpt-oss-120b` via the Groq API

## Limitations

- The topic restriction relies on a system prompt, so it is not unbreakable
- Answers can contain mistakes. In one test, an answer about RAG listed a product that is not a RAG tool, so check important details
- The chatbot runs in the terminal only and has no web interface
