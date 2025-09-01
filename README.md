# AI Agents and RAG: A Production-Focused Application Lifecycle

An end-to-end project implementing and rigorously evaluating two of the most critical applications in modern AI: **Retrieval-Augmented Generation (RAG)** and **Autonomous AI Agents**.

![Python Version](https://img.shields.io/badge/Python-3.8+-blue.svg)
![License](https://img.shields.io/badge/License-MIT-green.svg)
![Project Status](https://img.shields.io/badge/Status-Complete-brightgreen.svg)

This repository provides a comprehensive blueprint for the entire lifecycle of building sophisticated LLM applications. Moving beyond standard tutorials, it emphasizes robust architecture, modular implementation, and—most critically—**quantitative performance evaluation** to ensure production-readiness.

---

## Core Architecture

This project implements two primary, production-relevant architectural patterns:

1.  **Retrieval-Augmented Generation (RAG) Pipeline:** A system that grounds the LLM in external, private data to provide accurate, context-aware answers and mitigate hallucinations.
    ```
    User Query --> [Embedding Model] --> [Vector Database] --> [Retrieved Documents] --> [LLM] --> Synthesized Answer
    ```
2.  **Autonomous Agent with Tools:** An agent that can reason, plan, and autonomously use external tools (e.g., search, calculators) to solve complex, multi-step problems that an LLM alone cannot.
    ```
    User Goal --> [Agent (ReAct Logic)] --> [Tool Selection] --> [Tool Execution] --> [Observation] --> [LLM] --> Final Response
    ```

---

## Technical Features & Capabilities

-   **Structured LLM Control:** Implements advanced prompt engineering and output parsers to ensure reliable, structured, and predictable outputs from the language model.
-   **Stateful and Context-Aware Memory:** Integrates various memory modules (`ConversationBufferWindowMemory`, `ConversationSummaryBufferMemory`) for building stateful applications that can handle multi-turn conversations.
-   **Complex Workflow Orchestration:** Leverages LangChain's `SequentialChain` and `RouterChain` to architect and execute complex, multi-step logical workflows.
-   **End-to-End RAG Implementation:** Features a complete RAG pipeline, including document loading, chunking, embedding generation, vector storage, and semantic retrieval.
-   **Quantitative Evaluation Framework:** **(Key Differentiator)** Deploys a systematic evaluation pipeline using `QAGenerateChain` and `QAEvalChain` to quantitatively measure the accuracy and performance of the RAG system, a critical step for production deployment.
-   **Autonomous Agent Design:** Showcases the design of tool-augmented agents that can reason about a task and interact with external APIs to find solutions.

---

## Technology Stack

-   **Core Framework:** LangChain
-   **LLMs & Embeddings:** OpenAI (`gpt-4o`)
-   **Vector Storage:** DocArrayInMemorySearch
-   **Core Language:** Python 3.8+

---

## Implementation Modules

The project is broken down into a series of modules, each tackling a specific stage of the application lifecycle.

| Module | Notebook                                                                          | Core Objective                                                                                        |
| :----: | :-------------------------------------------------------------------------------- | :---------------------------------------------------------------------------------------------------- |
| **01** | [**Core LLM Abstractions**](./01_LangChain_Core_Components.ipynb)                   | Engineer the fundamental control layer: Models, Prompts, and Output Parsers.                          |
| **02** | [**Stateful Conversations**](./02_Stateful_Conversations_with_Memory.ipynb)         | Integrate memory modules to maintain conversational state and context.                                |
| **03** | [**Workflow Orchestration**](./03_Orchestrating_LLM_Workflows_with_Chains.ipynb)    | Architect complex, multi-step operations using a variety of chain types.                              |
| **04** | [**RAG Pipeline Construction**](./04_Question_Answering_over_Custom_Data.ipynb)     | Build the full RAG pipeline: ingest, embed, retrieve, and synthesize.                                 |
| **05** | [**Quantitative Evaluation**](./05_Evaluating_Q&A_System_Performance.ipynb)         | Implement a rigorous framework to quantitatively measure RAG system accuracy.                         |
| **06** | [**Autonomous Agent Design**](./06_Autonomous_Agents_with_Tools.ipynb)              | Deploy agents that leverage external tools to execute complex tasks autonomously.                     |

---

## Local Setup & Execution

### Prerequisites

-   Python 3.8+
-   An OpenAI API Key

### Installation

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/nabeelshan78/AI-Agents-and-RAG-Application-Lifecycle.git
    cd AI-Agents-and-RAG-Application-Lifecycle
    ```

2.  **Configure environment variables:**
    Create a `.env` file in the project root and add your API key:
    ```
    OPENAI_API_KEY="sk-..."
    ```

3.  **Launch the notebooks:**
    ```bash
    jupyter notebook
    ```
