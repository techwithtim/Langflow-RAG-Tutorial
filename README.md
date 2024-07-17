# Langflow-RAG-Tutorial

## Building an AI-Powered Chatbot Using LangFlow: A Step-by-Step Guide

[![Build a RAG Based LLM App in 20 Minutes! | Full Langflow Tutorial](https://img.youtube.com/vi/rz40ukZ3krQ/0.jpg)](https://www.youtube.com/watch?v=rz40ukZ3krQ)

This tutorial guides you through creating an AI application that utilizes [Retrieval-Augmented Generation (RAG)](https://www.pinecone.io/learn/retrieval-augmented-generation/) without writing any code. We'll use [LangFlow](https://docs.langflow.org/), a visual platform that makes building AI applications intuitive and straightforward.

<details>
<summary>Table of Contents</summary>

1. [Introduction](#introduction)
2. [Overview](#overview)
3. [Project Demo](#project-demo)
4. [Setup/Installation](#setupinstallation)
5. [Building a Basic Chatbot](#building-a-basic-chatbot)
6. [OpenAI Integration](#openai-integration)
7. [VectorStore Databases](#vectorstore-databases)
8. [Adding RAG](#adding-rag)
9. [Testing The App](#testing-the-app)
10. [Additional Features](#additional-features)
11. [Helpful Tips](#helpful-tips)
12. [Resources](#resources)

</details>

---

## Introduction

In this guide, we'll walk you through creating an AI application that utilizes Retrieval-Augmented Generation (RAG) without writing any code. We'll use LangFlow, a visual platform that makes building AI applications intuitive and straightforward.

---

## Overview

- **Video:** [Build a RAG Based LLM App in 20 Minutes! | Full Langflow Tutorial](https://www.youtube.com/watch?v=rz40ukZ3krQ)
- **Channel:** [Tech With Tim](https://www.youtube.com/c/TechWithTim)
- **Date:** 22 Apr 2024

<details>
<summary>Timestamps</summary>

- [00:00 | Overview](https://www.youtube.com/watch?v=rz40ukZ3krQ&t=0s)
- [00:33 | Project Demo](https://www.youtube.com/watch?v=rz40ukZ3krQ&t=33s)
- [02:14 | Setup/Installation](https://www.youtube.com/watch?v=rz40ukZ3krQ&t=134s)
- [04:07 | Building a Basic Chatbot](https://www.youtube.com/watch?v=rz40ukZ3krQ&t=247s)
- [09:27 | OpenAI Integration](https://www.youtube.com/watch?v=rz40ukZ3krQ&t=567s)
- [12:33 | VectorStore Databases](https://www.youtube.com/watch?v=rz40ukZ3krQ&t=753s)
- [15:00 | Adding RAG](https://www.youtube.com/watch?v=rz40ukZ3krQ&t=900s)
- [21:35 | Testing The App](https://www.youtube.com/watch?v=rz40ukZ3krQ&t=1295s)
- [23:02 | Additional Features](https://www.youtube.com/watch?v=rz40ukZ3krQ&t=1382s)

</details>

---

## Project Demo

In this section, you'll see a demo of the final AI application you'll be building. The application will be able to answer questions based on a provided PDF document using a chatbot interface.

### Watch the Demo

- **Timestamp:** [00:33](https://www.youtube.com/watch?v=rz40ukZ3krQ&t=33s)

---

## Setup/Installation

### Install LangFlow using pip.

### Ensure you have [Python 3.10](https://www.python.org/downloads/) or above installed.

- **Command to check Python version:**

```bash
python --version
```

or

```bash
python3 --version
```

- **If Python is not installed:**
  - **Download and install it from** [python.org](https://www.python.org/).
  - **Open your terminal and run the following command:**

```bash
pip install langflow --pre --force-reinstall
```

**Explanation:**

- `pip install` is the command to install Python packages.
- `langflow` is the name of the package.
- `--pre` allows the installation of pre-release versions.
- `--force-reinstall` forces the reinstallation of the package even if it's already installed.

### Run LangFlow locally.

- **Command to run LangFlow:**

```bash
langflow run
```

- **Open LangFlow in your browser:**
  - Navigate to `http://localhost:7860` if it doesn't open automatically.

### Watch the Setup

- **Timestamp:** [02:14](https://www.youtube.com/watch?v=rz40ukZ3krQ&t=134s)

---

## Building a Basic Chatbot

### Create a new flow.

- **Steps:**
  1. Click "New Project."
  2. Select "Blank Flow."

### Add text and chat inputs:

1. **From the sidebar, drag and drop the "Text Input" and "Chat Input" components.**
2. **Rename "Text Input" to "Name":**
   * Set it to capture the user's name.
3. **Connect the output of "Name" to the sender name input of "Chat Input."**

### Create a prompt template:

1. **Add a "Prompt" component.**
2. **Edit the template to include placeholders for context, question, and history:**

```markdown
Hey, answer the user's question based on the following context:
Context: {context}
Question: {question}
History: {history}
```

### Add chat memory:

1. **Drag and drop the "Chat Memory" component.**
2. **Connect the name input to the session ID of the chat memory.**

### Add a chat output:

1. **Drag and drop the "Chat Output" component.**
2. **Connect the output of the OpenAI component to the chat output.**
3. **Set the sender name to "AI."**

### Watch the Basic Chatbot Build

- **Timestamp:** [04:07](https://www.youtube.com/watch?v=rz40ukZ3krQ&t=247s)

---

## OpenAI Integration

### Create an OpenAI account.

- **Sign up at** [OpenAI](https://platform.openai.com/).

### Generate an OpenAI API key.

- **Steps:**
  1. Go to API keys in your OpenAI dashboard.
  2. Click "Create new secret key."
  3. Copy the generated key.

### Connect to OpenAI:

1. **Add an "OpenAI" component.**
2. **Paste your OpenAI API key in the appropriate field.**
3. **Connect the prompt to the OpenAI component.**

### Watch the OpenAI Integration

- **Timestamp:** [09:27](https://www.youtube.com/watch?v=rz40ukZ3krQ&t=567s)

---

## VectorStore Databases

### Create a free account on DataStax Astra.

- **Go to** [DataStax Astra](https://dtsx.io/3vZk6n2) **and sign up.**

### Create a new database.

- **Steps:**
  1. Click on "Create Database."
  2. Select "Serverless Vector Database."
  3. Name your database (e.g., "LangFlowTutorial").
  4. Choose your cloud provider and region.
  5. Click "Create Database."

### Configure Astra DB:

1. **Add an "Astra DB" component.**
2. **Enter your Astra DB endpoint, token, and collection name.**
3. **Connect the embeddings to the Astra DB component.**

### Watch the VectorStore Databases Setup

- **Timestamp:** [12:33](https://www.youtube.com/watch?v=rz40ukZ3krQ&t=753s)

---

## Adding RAG

### Load the PDF file:

1. **Add a "File Loader" component.**
2. **Upload your PDF file (e.g., restaurant Q&A).**

### Split the text:

1. **Add a "Split Text" component.**
2. **Connect the file loader to the split text component.**

### Set up OpenAI embeddings:

1. **Add an "OpenAI Embeddings" component.**
2. **Connect the split text output to the embeddings input.**

### Add a Vector Search component:

1. **Connect the chat input to the Vector Search component.**
2. **Connect the embeddings to the Vector Search component.**
3. **Connect the output of the Vector Search component to the prompt context input.**

### Watch Adding RAG

- **Timestamp:** [15:00](https://www.youtube.com/watch?v=rz40ukZ3krQ&t=900s)

---

## Testing The App

### Test the flow:

1. **Click "Run" at the top of the LangFlow interface.**
2. **Enter your name and ask a question (e.g., "What time are you open?").**

### Check for responses:

- **Ensure the chatbot responds correctly by utilizing the information from the PDF.**

### Watch Testing The App

- **Timestamp:** [21:35](https://www.youtube.com/watch?v=rz40ukZ3krQ&t=1295s)

---

## Additional Features

### Export your flow as JSON:

1. **Click "Export" and download the JSON file.**

### Import a flow:

1. **Click "Import" and upload the JSON file to load a pre-configured flow.**

### Watch Additional Features

- **Timestamp:** [23:02](https://www.youtube.com/watch?v=rz40ukZ3krQ&t=1382s)

---

## Helpful Tips

- **Stay Organized:** Use descriptive names for your components to keep track of their functions easily.
- **Test Frequently:** Regularly run your flow to ensure each component works as expected.
- **Explore LangFlow Documentation:** For more advanced features and troubleshooting.

---

## Resources

- **LangFlow Documentation/Installation:** [LangFlow Docs](https://docs.langflow.org/)
- **LangFlow GitHub:** [LangFlow GitHub](https://dtsx.io/3vR07qO)
- **Build now with Astra DB:** [Astra DB](https://dtsx.io/3vZk6n2)
- **OpenAI API Key:** [OpenAI API Key](https://platform.openai.com/api-keys)
- **Code/Flow File:** [GitHub Repository](https://github.com/techwithtim/Langflow-Tutorial)
- **Learn more about RAG:** [Retrieval-Augmented Generation](https://www.pinecone.io/learn/retrieval-augmented-generation/)
- **Python Downloads:** [Python.org](https://www.python.org/downloads/)

---

By following these steps, you can build and run an AI-powered chatbot using LangFlow without any programming knowledge. Enjoy creating your AI application and sharing it with others!
