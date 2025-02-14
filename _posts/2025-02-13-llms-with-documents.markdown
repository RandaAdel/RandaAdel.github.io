---
layout: post
title:  Talk to me (Well to my Chatbot) Context-Aware & Document-Savvy
date:   2025-02-13 12:05:55 +0300
image:  /assets/images/blog/llm-post.jpg
author: Randa Ahmed 
tags:   LLMs
---

**The best way to apply what you learn is through a project that truly interests you, and for me, that means exploring the potential of LLMs. Since I’m actively speaking with recruiters, I decided to build a chatbot that can handle questions about me during the initial recruitment stage. To make it truly effective, I gave it awareness of conversation history and provided it with documents about me, allowing it to deliver personalized and context-aware responses.**

<br><br><br>

***For the design phase of my project, I decided to divide it into two main stages:***
  &emsp; 1- Uploading and Structuring Data – This involves uploading my documents and storing them in a database, making them ready for retrieval, search, and any additional processing I decide to apply.
<br>
  &emsp; 2- Enhancing the LLM’s Capabilities – This stage focuses on providing the LLM model with all the necessary information, including context, conversation history, and the specific question, enabling it to generate meaningful and relevant responses.
<br>

***1- Uploading and Structuring Data:***
In this step I prepared the personal and professional information about me and I added them to some documents. 
<br>
  &emsp; • The available documents were uploaded to a dedicated directory. 
  <br>
  &emsp; • Each document was split into smaller chunks and converted into embeddings (refer to the note for more details).
  <br>
  &emsp; • The embeddings were then stored to a vector database (chroma in my case).
<p style="text-align: center;">
  <img src="/assets/images/blog/vector-db-pic.jpg" alt="Additional image description">
</p>

***2- Answer the asked question by the recruiter:***
In this step there are multiple components that I needed for the LLM to answer the question fluently. 
<br>
  &emsp; • The k relevant embeddings from the vector database were retrieved and concatenated as the "context". 
  <br>
  &emsp; • The recruiter's question was treated as the "query".
  <br>
  &emsp; • Any previous question or answer was fed to the model as "chat history".
  <br>
  &emsp; • Finally, the LLM combined all the components and generated an answer.
<p style="text-align: center;">
  <img src="/assets/images/blog/step-two-llm.jpg" alt="Additional image description">
</p>

To demonstrate how the system performs in real-world scenarios, I tested the chatbot with a question this morning. The chatbot successfully retrieved relevant information from the vector database and provided a well-structured response based on my uploaded documents. The conversation felt natural and contextually aware, showing that the retrieval and LLM processing worked as expected. Below is a screenshot from our chat. 
<p style="text-align: center;">
  <img src="/assets/images/blog/LLM-cov.jpg" alt="Additional image description">
</p>