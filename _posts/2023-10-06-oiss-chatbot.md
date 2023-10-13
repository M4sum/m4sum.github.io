---
layout: post
title: "OISS Chatbot"
---

## Table of contents
- [About](#about)
- [How It works](#how-it-works)

# [About](#about)

This chatbot allows users to ask immigration questions on their school’s OISS website. I developed the chatbot using LangCahin and Streamlit. It uses OpenAI’s chat completion API and allows you to have a conversational chat with an AI assistant powered by GPT-3.

# [How It works](#how-it-works)

1. The user enters a URL for their school’s OISS website. The app parses the URL recursively and extracts all the text content from the website.
2. This entire text content is then split into chunks for efficient processing.
3. These chunks are converted to embeddings using OpenAI’s “text-embedding-ada-002” model and stored in a vector database using Faiss. Faiss stores the embeddings locally, so it’s not the best choice for a production environment, but it works well for this app now. Subject to change soon.
4. When the user asks a question, the app compares it with the text chunks and identifies the most semantically similar ones.
5. It takes these selected embedding chunks and passes them to the GPT-3 API to generate a response.

You can check it out here: [OISS Chatbot](https://chat-with-oiss.streamlit.app/).