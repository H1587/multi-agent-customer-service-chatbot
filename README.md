# Multi-Agent Customer Service Chatbot

A customer service chatbot prototype built in Google Colab. LangGraph routes customer messages to specialist agents.

## Features
- **FAQ support:** Searches a small FAQ knowledge base using sentence-transformer embeddings and FAISS.
- **Order lookup:** Queries sample order records stored in SQLite.
- **Product recommendations:** Uses deterministic rules based on sample purchase history.
- **Intent routing:** Uses a Groq-hosted language model to route requests to the FAQ, order, or recommendation agent.
- **Chat interface:** Uses Gradio and conversation history to help resolve follow-up questions.

## Architecture
See [`docs/architecture.md`](docs/architecture.md).

## Running the notebook
The main implementation is [`Agentic_customer_service_bot.ipynb`](Agentic_customer_service_bot.ipynb).

The notebook was developed in Google Colab:
1. Open the notebook in Colab.
2. Configure a Groq API key securely using Colab Secrets or the runtime environment.
3. Run the notebook cells in order.
4. Launch the Gradio interface when you reach the interface section.

Never hard-code API keys into notebook cells or commit them to GitHub.

## Dependencies
See [`requirements.txt`](requirements.txt). Colab may already provide some dependencies. Check compatibility with the current runtime before installing all packages at once.

## Sample data and limitations
This prototype uses sample order records and a small FAQ knowledge base. It is not connected to a real commerce system.
- Tracking numbers and estimated delivery dates are not stored in the sample database.
- Recommendations are rule-based and do not establish a customer's actual interests.
- Conversation context is supplied by the Gradio session and is not durable across new sessions or runtime resets.
- This is a learning/demo prototype, not a production-ready customer service system.

## Security
- Never commit `.env` files, API keys, credentials, real customer records, or private runtime data.
- Review notebook outputs before publishing; outputs can accidentally contain secrets.
- This repository is public, so assume committed files are visible to anyone.

## Project status
Core prototype flows have been exercised. The latest tightening of the recommendation agent's system prompt has not been retested.
