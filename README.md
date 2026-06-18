# TypeScript LangChain AI Assistant with Chains, Memory, Agents, and LangSmith Debugging

## Overview

This project demonstrates how to build an AI-powered Study Assistant using LangChain and TypeScript. The application showcases the core concepts of modern AI development, including Chains, Memory, Agents, Tool Calling, Context Management, and LangSmith Tracing.

The assistant accepts user questions, processes them through LangChain workflows, remembers conversation history, and dynamically decides whether tools are required to answer a query.

---

# Application Output

## Interactive Study Assistant

The chatbot runs in interactive mode and accepts user questions from the terminal.

<img width="1600" height="735" alt="WhatsApp Image 2026-06-18 at 12 08 41 PM" src="https://github.com/user-attachments/assets/095ed87a-dc7e-48e4-a860-8b6ef9fa51ff" />


---

## Example Response – Chains vs Agents

The assistant explains concepts clearly using LangChain chains and agent workflows.

<img width="1600" height="580" alt="WhatsApp Image 2026-06-18 at 12 08 41 PM (1)" src="https://github.com/user-attachments/assets/493e7c64-7737-43be-888b-fd355145f759" />


---

# What Problem Does LangChain Solve?

Large Language Models can generate text responses, but production AI applications require much more functionality.

| Problem                | LangChain Solution |
| ---------------------- | ------------------ |
| Prompt Management      | Prompt Templates   |
| Multi-Step Workflows   | Chains             |
| Conversation History   | Memory             |
| Context Management     | Message History    |
| Tool Usage             | Agents             |
| Structured Output      | Output Parsers     |
| Monitoring & Debugging | LangSmith          |

Without LangChain, developers must implement these capabilities manually. LangChain provides a structured framework that simplifies AI application development.

---

# Why Developers Use LangChain

LangChain enables developers to:

* Build modular AI applications
* Create reusable prompt templates
* Maintain conversation memory
* Integrate external tools
* Build intelligent agents
* Monitor executions with LangSmith
* Support multiple LLM providers

These features reduce development complexity and improve scalability.

---

# Features

## Chains

Chains create fixed workflows where output from one component becomes input for the next component.

Example Flow:

```text id="o5jwyf"
User Question
      ↓
Prompt Template
      ↓
Language Model
      ↓
Response
```

Chains are useful when the workflow is predictable.

---

## Memory

Memory allows the assistant to remember previous interactions.

Example:

```text id="q4f8pm"
User: My name is Sam.

User: What is my name?

Assistant: Your name is Sam.
```

Memory improves conversation continuity and context awareness.

---

## Context Management

Conversation history is automatically preserved and injected into future prompts.

Benefits:

* Personalized responses
* Better user experience
* Multi-turn conversations
* Reduced repetition

---

## Agents

Agents dynamically decide which tool should be used to solve a user's request.

Example:

```text id="b57h5m"
User: What is 250 × 40?

Agent:
  → Detects mathematical operation
  → Calls Calculator Tool
  → Returns result
```

Unlike chains, agents can choose actions at runtime.

---

## Tools

### Calculator Tool

Used for mathematical calculations.

Example:

```text id="pcz4km"
User: Calculate 150 + 350

Result: 500
```

### Study Tips Tool

Provides educational guidance and study recommendations.

Example:

```text id="0of9l2"
User: Give me study tips

Assistant:
• Study daily
• Practice consistently
• Revise regularly
```

---

# Application Architecture

```text id="1kpkzq"
User Input
    │
    ▼
Prompt Template
    │
    ▼
Chain
    │
    ▼
Memory
    │
    ▼
Language Model
    │
    ▼
Agent Decision
    │
 ┌──┴─────────────┐
 │                │
 ▼                ▼
Calculator      Study Tool
 │                │
 └──────┬─────────┘
        ▼
 Final Response
        │
        ▼
 LangSmith Trace
```

---

# LangSmith Debugging

LangSmith provides observability for LangChain applications.

It records:

* Prompt execution
* Agent decisions
* Tool invocations
* Model outputs
* Errors
* Token usage

---

## Why LangSmith Matters

Without LangSmith:

```text id="k2xscm"
Agent produced wrong answer
↓
Cause unknown
```

With LangSmith:

```text id="gyk3fc"
Agent produced wrong answer
↓
View trace
↓
Inspect prompt
↓
Inspect tool call
↓
Identify issue
```

---

## Example Trace Flow

```text id="r5tmvt"
User Input
│
├── Prompt Template
│
├── LLM Call
│
├── Agent Decision
│
├── Tool Execution
│
└── Final Response
```

LangSmith makes debugging and optimization significantly easier.

---

# Project Structure

```text id="9zv1lv"
AI-Study-Assistant/

src/
├── index.ts
├── models.ts
├── prompts.ts
├── chains.ts
├── memory.ts
├── tools.ts
├── agent.ts
├── langsmith.ts
├── config.ts

screenshots/
├── op1.png
├── op2.png

.env
.env.example
README.md
package.json
tsconfig.json
```

# Technologies Used

| Technology         | Purpose                   |
| ------------------ | ------------------------- |
| TypeScript         | Type-safe development     |
| LangChain          | AI application framework  |
| OpenAI GPT-4o Mini | Language model            |
| LangSmith          | Tracing and debugging     |
| Node.js            | Runtime environment       |
| Zod                | Schema validation         |
| dotenv             | Environment management    |
| MathJS             | Mathematical calculations |

---

# Installation

## Clone Repository

```bash id="lby1ri"
git clone <repository-url>
cd AI-Study-Assistant
```

## Install Dependencies

```bash id="0t39o2"
npm install
```

## Configure Environment Variables

Create a `.env` file:

```env id="nnr13n"
OPENAI_API_KEY=your_openai_api_key

LANGCHAIN_TRACING_V2=true
LANGCHAIN_API_KEY=your_langsmith_api_key
LANGCHAIN_PROJECT=study-assistant
```

---

# Running the Application

Start the chatbot:

```bash id="3kgw78"
npm run dev
```

---

# Example Usage

### Explain a Concept

```text id="jlwmf9"
You: Explain recursion

Assistant:
Recursion is a programming technique where a function calls itself to solve a problem.
```

### Mathematical Query

```text id="c0j5q0"
You: What is 125 × 45?

Assistant:
5625
```

### Study Help

```text id="mt7dmh"
You: Give me study tips

Assistant:
1. Create a schedule
2. Revise regularly
3. Practice problems
```

---

# Learning Outcomes

This project demonstrates:

* Prompt Engineering
* Chains
* Memory Management
* Context Handling
* Agent Design
* Tool Calling
* LangSmith Tracing
* TypeScript AI Development

---

# Future Improvements

* Retrieval-Augmented Generation (RAG)
* PDF Question Answering
* Vector Databases
* Multi-Agent Systems
* Web Search Integration
* Voice Assistant Support

---

# Conclusion

This project demonstrates how LangChain simplifies the development of intelligent AI assistants. By combining Chains, Memory, Agents, and LangSmith tracing, developers can create scalable and maintainable AI applications capable of handling real-world use cases.

---

# License

MIT License
