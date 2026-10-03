# 📘 LangChain Mastery

> Professional README for `Langchain.pdf`

A practical learning resource covering the major building blocks of
**LangChain and LLM application development**, from models and prompts
to RAG, tools, agents, memory, callbacks, and LangGraph.

## 📌 Overview

The resource explains how LangChain provides reusable components for
connecting:

``` text
Models + Prompts + Data + Retrieval + Memory + Tools
                         ↓
                 LLM Applications
```

It progresses from individual components to a complete conversational
RAG application.

## 🎯 Topics Covered

-   LangChain fundamentals
-   Models and Chat Models
-   Prompt Templates
-   Output Parsers
-   Runnables and LCEL
-   Memory
-   Document Loaders
-   Text Splitters
-   Embeddings
-   Vector Stores
-   Retrievers
-   Chains
-   Tools
-   Agents
-   Callbacks
-   LangGraph
-   RAG application development

## 🧩 Core Components

  Component          Purpose
  ------------------ -------------------------------------------
  Models             Interface with LLMs and chat models
  Prompts            Create reusable model inputs
  Output Parsers     Convert model output into structured data
  Runnables / LCEL   Compose components into pipelines
  Memory             Maintain conversation state
  Document Loaders   Load external data
  Text Splitters     Break documents into useful chunks
  Embeddings         Convert text into semantic vectors
  Vector Stores      Store and search vectors
  Retrievers         Fetch relevant documents
  Chains             Build multi-step workflows
  Tools              Let models interact with external systems
  Agents             Dynamically choose tools and actions
  Callbacks          Logging, streaming, monitoring, debugging
  LangGraph          Stateful and cyclical workflows

## 🤖 Models

LangChain supports a common interface for language models and chat
models.

A major benefit is that application logic can remain similar while
changing the underlying model provider.

## 📝 Prompts

Prompt templates make prompts reusable, parameterized, and easier to
test.

``` python
from langchain_core.prompts import ChatPromptTemplate

prompt = ChatPromptTemplate.from_messages([
    ("system", "You are a helpful {role}."),
    ("human", "{question}")
])
```

## 📤 Output Parsers

Output parsers convert raw model responses into formats that application
code can use.

Common examples:

-   `StrOutputParser`
-   `JsonOutputParser`
-   `PydanticOutputParser`

Typical pattern:

``` text
Prompt → Model → Parser
```

## 🔗 LCEL

**LangChain Expression Language (LCEL)** uses the `|` operator to
compose components.

``` python
chain = prompt | model | parser
result = chain.invoke({
    "role": "tutor",
    "question": "Explain embeddings"
})
```

Runnables commonly support `.invoke()`, `.stream()`, and `.batch()`.

## 🧠 Memory

Memory allows an application to use previous conversation turns. The
resource demonstrates `RunnableWithMessageHistory` for multi-turn
applications.

## 📄 Document Loaders

Document loaders convert external sources into LangChain documents.

Examples:

-   `PyPDFLoader`
-   `WebBaseLoader`
-   `CSVLoader`
-   `DirectoryLoader`

``` text
External Data → Document Loader → LangChain Documents
```

## ✂️ Text Splitters

Large documents are divided into smaller chunks for retrieval.

``` python
from langchain_text_splitters import RecursiveCharacterTextSplitter

splitter = RecursiveCharacterTextSplitter(
    chunk_size=500,
    chunk_overlap=50
)
```

Good chunking is important for retrieval quality.

## 🔢 Embeddings

Embeddings convert text into numerical vectors representing semantic
meaning.

``` text
Text → Embedding Model → Vector
```

## 🗄️ Vector Stores

Vector stores save embeddings and support similarity search.

Examples covered include Chroma, FAISS, Pinecone, and Qdrant.

## 🔎 Retrievers

Retrievers fetch relevant documents for a query.

``` python
retriever = vectorstore.as_retriever(
    search_kwargs={"k": 4}
)

docs = retriever.invoke("What is the refund policy?")
```

Advanced concepts include query expansion and contextual
compression/reranking.

## 🔗 Chains

Chains represent multi-step workflows.

``` text
User Query
    ↓
Retriever
    ↓
Relevant Documents
    ↓
Prompt
    ↓
LLM
    ↓
Answer
```

## 🛠️ Tools

Tools are functions an LLM can call to interact with external systems
such as APIs, search engines, calculators, and databases.

``` python
from langchain_core.tools import tool

@tool
def get_weather(city: str) -> str:
    return f"Weather information for {city}"
```

## 🤖 Agents

Agents dynamically decide which tools to use and in what order.

``` text
User Request
     ↓
Agent
     ↓
Choose Tool
     ↓
Tool Result
     ↓
Reason / Continue
     ↓
Final Answer
```

## 📊 Callbacks

Callbacks provide observability for logging, streaming, monitoring,
debugging, and tracking intermediate execution.

## 🧠 LangGraph

LangGraph is introduced for more complex stateful workflows involving
branching, loops, complex agents, multi-agent systems, and
human-in-the-loop steps.

## 🚀 Complete RAG Project

The resource builds a company FAQ RAG application.

``` text
FAQ Document
     ↓
Document Loader
     ↓
Text Splitter
     ↓
Embeddings
     ↓
Vector Store
     ↓
Retriever
     ↓
Prompt + Context
     ↓
LLM
     ↓
Grounded Answer
     ↓
Conversation Memory
```

## 💡 Practice Projects

-   PDF Question Answering
-   Conversational RAG Chatbot
-   Company FAQ Assistant
-   Multi-document Research Assistant
-   Semantic Search Application
-   Tool-Calling AI Agent
-   Memory-Enabled Chatbot
-   API-Calling Agent

## 📚 Purpose

This README is a professional companion to `Langchain.pdf`. The PDF
contains detailed explanations, code examples, cheatsheets, and a
complete RAG walkthrough.

## 👨‍💻 Author

**Srivardhan Jilla**

AI / Machine Learning / Generative AI Enthusiast

-   GitHub: https://github.com/jillasrivardhan
-   LinkedIn: https://www.linkedin.com/in/jilla-srivardhan/
