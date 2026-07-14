# AI Learning Repository

This repository contains my end-to-end AI learning journey, from AI fundamentals to building production-ready AI applications using Flowise, LangChain, LangGraph, Spring AI, MCP, RAG, and Vector Databases.

The documentation is organized so that every concept has a single responsibility. Before reading any topic, use the guide below to know which document to refer.

---

# Repository Structure

```
AI
│
├── Agentic AI
├── AI Agents
├── Docker
├── Flowise
│   ├── flowise_nodes
│   ├── chatflow.txt
│   ├── Flowise_Notes.txt
│   └── manual_mapping.txt
│
├── LangChain
├── LangGraph
├── LLM
├── MCP
├── Projects
├── RAG
├── Vector Database
└── README.md
```

---

# Documentation Guide

## Flowise

### flowise_nodes/

Purpose

- Contains documentation for every Flowise node.
- One document per node.
- Explains only that node.

Example

```
Chat Model
Buffer Memory
Conversation Chain
Retriever
Vector Store
Tool
Agent
...
```

Open this folder when you want to understand a particular node.

---

### chatflow.txt

Purpose

- Contains all hands-on tasks.
- Every task is explained step by step.
- A beginner can build the complete application by following this document.

Each task contains

- Objective
- Architecture
- Components
- Execution Flow
- Current Chatflow
- Difference from Previous Task
- Important Notes

Open this document when you want to build an AI application.

---

### Flowise_Notes.txt

Purpose

- Contains Flowise fundamentals.
- Explains concepts related to Flowise itself.

Examples

- What is Flowise?
- Chatflow vs Agentflow
- LangChain Integration
- LangGraph Integration
- Credentials
- Workspace
- Deployment
- Export / Import

Open this document when learning Flowise concepts.

---

### manual_mapping.txt

Purpose

- Maps every Flowise node to its equivalent implementation.
- Used during manual implementation using Spring AI, LangChain4j, or other frameworks.

Examples

```
Flowise
        ⇔
Spring AI
        ⇔
LangChain4j
```

Example Mapping

```
Chat Model
        ⇔
ChatModel

Buffer Memory
        ⇔
ChatMemory

Conversation Chain
        ⇔
ChatClient
        +
PromptTemplate
        +
ChatMemory
```

Open this document while implementing AI applications manually.

---

# Docker

Contains Docker fundamentals, commands, hands-on examples, and notes required for running AI applications locally.

---

# LangChain

Contains concepts, architecture, components, and implementation related to LangChain.

---

# LangGraph

Contains concepts and implementation of multi-agent workflows using LangGraph.

---

# LLM

Contains LLM fundamentals including

- Tokens
- Embeddings
- Temperature
- Context Window
- Prompt Engineering
- Inference
- Fine Tuning

---

# MCP

Contains Model Context Protocol concepts and implementation.

---

# RAG

Contains Retrieval-Augmented Generation concepts, implementation, and projects.

---

# Vector Database

Contains Vector Database concepts, embeddings, indexing, similarity search, and implementation.

---

# Projects

Contains complete AI project implementations with architecture and documentation.

---

# Which Document Should I Read?

| Goal | Document |
|------|----------|
| Understand a Flowise Node | `flowise_nodes/` |
| Build an AI Application Step by Step | `chatflow.txt` |
| Learn Flowise Concepts | `Flowise_Notes.txt` |
| Implement using Spring AI / LangChain4j | `manual_mapping.txt` |
| Learn Docker | `Docker/` |
| Learn LangChain | `LangChain/` |
| Learn LangGraph | `LangGraph/` |
| Learn RAG | `RAG/` |
| Learn Vector Databases | `Vector Database/` |
| Build Complete AI Projects | `Projects/` |

---

# Learning Strategy

The learning journey follows this sequence:

```
Understand the Concept
        ↓
Learn Individual Nodes
        ↓
Build the Chatflow
        ↓
Understand Manual Mapping
        ↓
Implement using Spring AI / LangChain4j
        ↓
Build Real-world AI Projects
```

This structure ensures that concepts, implementation, and projects remain independent, making the repository easy to navigate, maintain, and revise.