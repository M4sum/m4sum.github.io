---
layout: post
title: "OISS Chatbot"
---

## Table of contents
- [Introduction](#introduction)
- [How It works](#how-it-works)

# [About](#introduction)

This is a chatbot that allows users to ask immigration questions to their school's OISS website. The chatbot is built using LangCahin and Streamlit. It uses OpenAI's chat completion API and  allows you to have a conversational chat with an AI assistant powered by GPT-3. The overall process is pretty simple and can e broken down to these steps:

# [How It works](#how-it-works)

1. The user enters a URL for their school's OISS website. the app parses the URL recursively and extracts all the text content form the website.

2. This entire text content is then split into chunks for efficient processing.

3. These chunks are converted to embeddings using OpenAI's "text-embedding-ada-002" model, and stored into a vector database using Faiss. Faiss stores  the embeddings locally so its not the best choice for a production environment, but it works well for this app for now. Subject to change soon.

4. When the user asks a question, the app compares it with the text chunks and identifies the most semantically similar ones. 

5. It takes these selected embedding chunks and passed to the GPT-3 API to generate a response.

You can check it out here [OISS Chatbot](https://chat-with-oiss.streamlit.app/)