# Langflow-RAG-Tutorial

# **Building an AI-Powered Chatbot Using LangFlow: A Step-by-Step Guide**

## Introduction

In this guide, we'll walk you through creating an AI application that utilizes Retrieval-Augmented Generation (RAG) without writing any code. We'll use LangFlow, a visual platform that makes building AI applications intuitive and straightforward.

## Table of Contents

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

---

## Overview

* **Video:** [Build a RAG Based LLM App in 20 Minutes! | Full Langflow Tutorial](https://www.youtube.com/watch?v=rz40ukZ3krQ)
* **Channel:** Tech With Tim
* **Date:** 22 Apr 2024
* **Timestamps:**
  * 00:00 | Overview
  * 00:33 | Project Demo
  * 02:14 | Setup/Installation
  * 04:07 | Building a Basic Chatbot
  * 09:27 | OpenAI Integration
  * 12:33 | VectorStore Databases
  * 15:00 | Adding RAG
  * 21:35 | Testing The App
  * 23:02 | Additional Features

---

## **Step 1: Project Demo (00:33)**

In this section, you'll see a demo of the final AI application you'll be building. The application will be able to answer questions based on a provided PDF document using a chatbot interface.

### Watch the Demo

* **Timestamp:** [00:33](https://www.youtube.com/watch?v=rz40ukZ3krQ&t=33s)

---

## **Step 2: Setup/Installation (02:14)**

### Ensure you have Python 3.10 or above installed.

* **Command to check Python version:**

  or

<pre><div class="dark bg-gray-950 rounded-md border-[0.5px] border-token-border-medium"><div class="flex items-center relative text-token-text-secondary bg-token-main-surface-secondary px-4 py-2 text-xs font-sans justify-between rounded-t-md"><span>bash</span><div class="flex items-center"><span class="" data-state="closed"><button class="flex gap-1 items-center"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="none" viewBox="0 0 24 24" class="icon-sm"><path fill="currentColor" fill-rule="evenodd" d="M7 5a3 3 0 0 1 3-3h9a3 3 0 0 1 3 3v9a3 3 0 0 1-3 3h-2v2a3 3 0 0 1-3 3H5a3 3 0 0 1-3-3v-9a3 3 0 0 1 3-3h2zm2 2h5a3 3 0 0 1 3 3v5h2a1 1 0 0 0 1-1V5a1 1 0 0 0-1-1h-9a1 1 0 0 0-1 1zM5 9a1 1 0 0 0-1 1v9a1 1 0 0 0 1 1h9a1 1 0 0 0 1-1v-9a1 1 0 0 0-1-1z" clip-rule="evenodd"></path></svg>Copy code</button></span></div></div><div class="overflow-y-auto p-4" dir="ltr"><code class="!whitespace-pre hljs language-bash">python3 --version
  </code></div></div></pre>

* **If Python is not installed:**
  * Download and install it from** **[python.org](https://www.python.org/).

### Install LangFlow using pip.

* **Open your terminal and run the following command:**

<pre><div class="dark bg-gray-950 rounded-md border-[0.5px] border-token-border-medium"><div class="flex items-center relative text-token-text-secondary bg-token-main-surface-secondary px-4 py-2 text-xs font-sans justify-between rounded-t-md"><span>bash</span><div class="flex items-center"><span class="" data-state="closed"><button class="flex gap-1 items-center"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="none" viewBox="0 0 24 24" class="icon-sm"><path fill="currentColor" fill-rule="evenodd" d="M7 5a3 3 0 0 1 3-3h9a3 3 0 0 1 3 3v9a3 3 0 0 1-3 3h-2v2a3 3 0 0 1-3 3H5a3 3 0 0 1-3-3v-9a3 3 0 0 1 3-3h2zm2 2h5a3 3 0 0 1 3 3v5h2a1 1 0 0 0 1-1V5a1 1 0 0 0-1-1h-9a1 1 0 0 0-1 1zM5 9a1 1 0 0 0-1 1v9a1 1 0 0 0 1 1h9a1 1 0 0 0 1-1v-9a1 1 0 0 0-1-1z" clip-rule="evenodd"></path></svg>Copy code</button></span></div></div><div class="overflow-y-auto p-4" dir="ltr"><code class="!whitespace-pre hljs language-bash">pip install langflow --pre --force-reinstall
  </code></div></div></pre>

**Explanation:**

* `pip install` is the command to install Python packages.
* `langflow` is the name of the package.
* `--pre` allows the installation of pre-release versions.
* `--force-reinstall` forces the reinstallation of the package even if it's already installed.

### Watch the Setup

* **Timestamp:** [02:14](https://www.youtube.com/watch?v=rz40ukZ3krQ&t=134s)

---

## **Step 3: Building a Basic Chatbot (04:07)**

### Run LangFlow locally.

* **Command to run LangFlow:**

<pre><div class="dark bg-gray-950 rounded-md border-[0.5px] border-token-border-medium"><div class="flex items-center relative text-token-text-secondary bg-token-main-surface-secondary px-4 py-2 text-xs font-sans justify-between rounded-t-md"><span>bash</span><div class="flex items-center"><span class="" data-state="closed"><button class="flex gap-1 items-center"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="none" viewBox="0 0 24 24" class="icon-sm"><path fill="currentColor" fill-rule="evenodd" d="M7 5a3 3 0 0 1 3-3h9a3 3 0 0 1 3 3v9a3 3 0 0 1-3 3h-2v2a3 3 0 0 1-3 3H5a3 3 0 0 1-3-3v-9a3 3 0 0 1 3-3h2zm2 2h5a3 3 0 0 1 3 3v5h2a1 1 0 0 0 1-1V5a1 1 0 0 0-1-1h-9a1 1 0 0 0-1 1zM5 9a1 1 0 0 0-1 1v9a1 1 0 0 0 1 1h9a1 1 0 0 0 1-1v-9a1 1 0 0 0-1-1z" clip-rule="evenodd"></path></svg>Copy code</button></span></div></div><div class="overflow-y-auto p-4" dir="ltr"><code class="!whitespace-pre hljs language-bash">langflow run
  </code></div></div></pre>

* **Open LangFlow in your browser:**
  * Navigate to** **`http://localhost:7860` if it doesn’t open automatically.

### Create a new flow.

* **Steps:**
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

<pre><div class="dark bg-gray-950 rounded-md border-[0.5px] border-token-border-medium"><div class="flex items-center relative text-token-text-secondary bg-token-main-surface-secondary px-4 py-2 text-xs font-sans justify-between rounded-t-md"><span>markdown</span><div class="flex items-center"><span class="" data-state="closed"><button class="flex gap-1 items-center"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="none" viewBox="0 0 24 24" class="icon-sm"><path fill="currentColor" fill-rule="evenodd" d="M7 5a3 3 0 0 1 3-3h9a3 3 0 0 1 3 3v9a3 3 0 0 1-3 3h-2v2a3 3 0 0 1-3 3H5a3 3 0 0 1-3-3v-9a3 3 0 0 1 3-3h2zm2 2h5a3 3 0 0 1 3 3v5h2a1 1 0 0 0 1-1V5a1 1 0 0 0-1-1h-9a1 1 0 0 0-1 1zM5 9a1 1 0 0 0-1 1v9a1 1 0 0 0 1 1h9a1 1 0 0 0 1-1v-9a1 1 0 0 0-1-1z" clip-rule="evenodd"></path></svg>Copy code</button></span></div></div><div class="overflow-y-auto p-4" dir="ltr"><code class="!whitespace-pre hljs language-markdown">Hey, answer the user's question based on the following context:
   Context: {context}
   Question: {question}
   History: {history}
   </code></div></div></pre>

### Add chat memory:

1. **Drag and drop the "Chat Memory" component.**
2. **Connect the name input to the session ID of the chat memory.**

### Add a chat output:

1. **Drag and drop the "Chat Output" component.**
2. **Connect the output of the OpenAI component to the chat output.**
3. **Set the sender name to "AI."

### Watch the Basic Chatbot Build

* **Timestamp:** [04:07](https://www.youtube.com/watch?v=rz40ukZ3krQ&t=247s)

**Explanation:**

* These steps involve adding and connecting components that will allow the chatbot to capture user input, process it, store conversation history, and respond using OpenAI's language model.

---

## **Step 4: OpenAI Integration (09:27)**

### Create an OpenAI account.

* **Sign up at** [OpenAI](https://platform.openai.com/).

### Generate an OpenAI API key.

* **Steps:**
  1. Go to API keys in your OpenAI dashboard.
  2. Click "Create new secret key."
  3. Copy the generated key.

### Connect to OpenAI:

1. **Add an "OpenAI" component.**
2. **Paste your OpenAI API key in the appropriate field.**
3. **Connect the prompt to the OpenAI component.

### Watch the OpenAI Integration

* **Timestamp:** [09:27](https://www.youtube.com/watch?v=rz40ukZ3krQ&t=567s)

**Explanation:**

* An API key is a code passed in by computer programs calling an API (Application Programming Interface) to identify the calling program.

---

## **Step 5: VectorStore Databases (12:33)**

### Create a free account on DataStax Astra.

* **Go to** [DataStax Astra]() **and sign up.**

### Create a new database.

* **Steps:**
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

* **Timestamp:** [12:33](https://www.youtube.com/watch?v=rz40ukZ3krQ&t=753s)

**Explanation:**

* This process sets up a database that will store and retrieve data efficiently using vectors, which are used in AI to find relevant information quickly.

---

## **Step 6: Adding RAG (15:00)**

### Load the PDF file:

1. **Add a "File Loader" component.**
2. **Upload your PDF file (e.g., restaurant Q&A).**

### Split the text:

1. **Add a "Split Text" component.**
2. **Connect the file loader to the split text component.**

### Set up OpenAI embeddings:

1. **Add an "OpenAI Embeddings" component.**
2. **Connect the split text output to the embeddings input.

### Add a Vector Search component:

1. **Connect the chat input to the Vector Search component.**
2. **Connect the embeddings to the Vector Search component.**
3. **Connect the output of the Vector Search component to the prompt context input.

### Watch Adding RAG

* **Timestamp:** [15:00](https://www.youtube.com/watch?v=rz40ukZ3krQ&t=900s)

**Explanation:**

* **File Loader** : Uploads the document that contains information the chatbot will use.
* **Split Text** : Breaks the document into smaller, manageable pieces.
* **OpenAI Embeddings** : Converts the text pieces into vectors.
* **Vector Search** : Uses these vectors to find relevant information when the chatbot needs to answer questions.

---

## **Step 7: Testing The App (21:35)**

### Test the flow:

1. **Click "Run" at the top of the LangFlow interface.**
2. **Enter your name and ask a question (e.g., "What time are you open?").**

### Check for responses:

* **Ensure the chatbot responds correctly by utilizing the information from the PDF.**

### Watch Testing The App

* **Timestamp:** [21:35](https://www.youtube.com/watch?v=rz40ukZ3krQ&t=1295s)

**Explanation:**

* Running the flow allows you to test the chatbot and see if it responds with relevant information based on the provided document.

---

## **Step 8: Additional Features (23:02)**

### Export your flow as JSON:

1. **Click "Export" and download the JSON file.**

### Import a flow:

1. **Click "Import" and upload the JSON file to load a pre-configured flow.

### Watch Additional Features

* **Timestamp:** [23:02](https://www.youtube.com/watch?v=rz40ukZ3krQ&t=1382s)

**Explanation:**

* **Export** : Saves your flow configuration as a JSON file, which can be shared or backed up.
* **Import** : Loads a flow from a JSON file, making it easy to use pre-built configurations or share with others.

---

## **Helpful Tips**

* **Stay Organized:** Use descriptive names for your components to keep track of their functions easily.
* **Test Frequently:** Regularly run your flow to ensure each component works as expected.
* **Explore LangFlow Documentation:** For more advanced features and troubleshooting.

---

By following these steps, you can build and run an AI-powered chatbot using LangFlow without any programming knowledge. Enjoy creating your AI application and sharing it with others!

---

## Resources

* **LangFlow Documentation/Installation:** [LangFlow Docs](https://docs.langflow.org/)
* **LangFlow GitHub:** [LangFlow GitHub](https://dtsx.io/3vR07qO)
* **Build now with Astra DB:** [Astra DB](https://dtsx.io/3vZk6n2)
* **OpenAI API Key:** [OpenAI API Key](https://platform.openai.com/api-keys)
* **Code/Flow File:** [GitHub Repository](https://github.com/techwithtim/Langflow-Tutorial)

---

## YouTube Video

Watch the full tutorial video here: [Build a RAG Based LLM App in 20 Minutes! | Full Langflow Tutoria](https://www.youtube.com/watch?v=rz40ukZ3krQ)

## FootNotes

#### Here is a simple footnote[^1].

#### A footnote can also have multiple lines[^2].

[^1]: My reference.

[^2]: To add line breaks within a footnote, prefix new lines with 2 spaces.
