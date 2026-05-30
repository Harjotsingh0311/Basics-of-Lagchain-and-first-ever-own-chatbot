# 🚀 LangChain Basics: Build Your First AI Chatbot with Groq

A beginner-friendly project demonstrating the fundamentals of LangChain by building a simple AI chatbot using Groq's ultra-fast inference and Streamlit.

This project is designed for students who are starting their Generative AI and Agentic AI journey and want to understand how LangChain works under the hood.

---

## 📚 Learning Objectives

By completing this project, students will learn:

- What LangChain is
- How LLM applications are built
- How to connect Groq models using LangChain
- Prompt Engineering Basics
- Prompt Templates
- Output Parsers
- Chains
- Streaming Responses
- Building a Chat Interface using Streamlit
- Managing Chat History using Session State

---

## 🏗️ Project Structure

```bash
GEN_AGENTICAI/
│
├── .venv/
│
├── 1_Langchain_Basics/
│   ├── .env
│   ├── langchainbasics.ipynb
│   └── qachatbot.py
│
├── pyproject.toml
├── uv.lock
├── requirements.txt
├── README.md
└── .gitignore
```

---

# 🧠 Concepts Covered

## 1. LangChain

LangChain is a framework that helps developers build applications powered by Large Language Models (LLMs).

Instead of directly calling an API, LangChain provides:

- Prompt Templates
- Chains
- Memory
- Agents
- Tool Calling
- Retrieval Augmented Generation (RAG)

---

## 2. Groq

Groq provides ultra-fast inference for open-source language models.

We use Groq as our LLM provider.

Example:

```python
from langchain_groq import ChatGroq

model = ChatGroq(
    model="llama-3.3-70b-versatile"
)
```

---

## 3. Prompt Templates

Prompt Templates allow dynamic prompt generation.

Example:

```python
from langchain_core.prompts import ChatPromptTemplate

prompt = ChatPromptTemplate.from_messages([
    ("system","You are a helpful AI assistant"),
    ("user","{question}")
])
```

---

## 4. Output Parsers

Output Parsers convert model responses into usable formats.

Example:

```python
from langchain_core.output_parsers import StrOutputParser

parser = StrOutputParser()
```

---

## 5. Chains

A chain connects multiple LangChain components together.

Example:

```python
chain = prompt | model | parser
```

Flow:

User Input
↓
Prompt Template
↓
LLM
↓
Output Parser
↓
Final Response

---

# 🚀 Installation Guide

## Step 1: Clone Repository

```bash
git clone https://github.com/YOUR_USERNAME/langchain-basics-chatbot.git
```

Move into project directory:

```bash
cd langchain-basics-chatbot
```

---

## Step 2: Create Virtual Environment

Using UV:

```bash
uv venv
```

Activate:

### Windows

```bash
.venv\Scripts\activate
```

### Linux / Mac

```bash
source .venv/bin/activate
```

---

## Step 3: Install Dependencies

Using UV:

```bash
uv sync
```

OR

```bash
pip install -r requirements.txt
```

---

## Step 4: Create Environment File

Create:

```bash
.env
```

Add:

```env
GROQ_API_KEY=your_groq_api_key
```

Get your API key:

https://console.groq.com

---

## Step 5: Run Application

```bash
streamlit run qachatbot.py
```

Open:

```text
http://localhost:8501
```

---

# 💻 Example Usage

Ask:

```text
What is LangChain?
```

Ask:

```text
Explain Prompt Engineering
```

Ask:

```text
What is the difference between LangChain and LangGraph?
```

Ask:

```text
Write a poem about AI
```

---

# 🔄 How The Chatbot Works

## Step 1

User enters a question.

```python
question = st.chat_input()
```

---

## Step 2

Prompt Template formats the request.

```python
prompt = ChatPromptTemplate.from_messages(...)
```

---

## Step 3

LangChain sends prompt to Groq.

```python
llm = ChatGroq(...)
```

---

## Step 4

Response is streamed.

```python
for chunk in chain.stream():
```

---

## Step 5

Response is displayed inside Streamlit.

```python
st.chat_message("assistant")
```

---

# 🧪 Models Tested

Recommended:

```text
llama-3.3-70b-versatile
```

Also Supported:

```text
llama-3.1-8b-instant
openai/gpt-oss-20b
openai/gpt-oss-120b
```

---

# ⚠️ Common Errors

## 1. Missing API Key

Error:

```text
APIConnectionError
```

Solution:

Check `.env`

```env
GROQ_API_KEY=your_key
```

---

## 2. Missing Package

Error:

```text
ModuleNotFoundError
```

Solution:

```bash
pip install langchain-groq
```

---

## 3. Model Decommissioned

Error:

```text
model_decommissioned
```

Solution:

Use a supported model.

Example:

```text
llama-3.3-70b-versatile
```

---

# 🎓 What Students Learned

After completing this project students understand:

✅ Environment Setup

✅ UV Package Manager

✅ LangChain Basics

✅ Groq Integration

✅ Prompt Templates

✅ Output Parsers

✅ Chains

✅ Streaming

✅ Session State

✅ Streamlit

✅ Building AI Chatbots

---

# 🏆 Author

Harjot Singh

B.Tech AIML | Thapar University

Learning Generative AI, Agentic AI, LangChain, LangGraph, Computer Vision, and AI Systems.

---
