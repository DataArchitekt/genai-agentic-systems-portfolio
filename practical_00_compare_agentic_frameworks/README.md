<<<<<<< HEAD
# GenAI & Agentic Systems – Practical Portfolio

## Who This Repo Is For

Hiring managers, AI leads, and architects evaluating real-world GenAI capability.


## What This Repo Demonstrates
- Agentic reasoning (ReAct, Reflection)
- Tool routing & orchestration
- Memory & conversation persistence
- Structured outputs for business use cases

## Practical Projects
1. Startup Research Copilot (ReAct + Router + Memory)
2. \<Practical 2 name>

## Tech Stack
Python | LangChain | OpenAI | Vector DB | Tools | Prompt Engineering

## How to Navigate

Each project folder contains:
- Problem statement
- Architecture
- Execution steps
- Sample outputs
=======
This practical demonstrates and compares three popular agentic AI frameworks using a single Jupyter notebook.
The goal is to understand how different frameworks implement agent behavior, their strengths, limitations, and suitability for real-world use cases.

The notebook contains three self-contained sections, each implementing the same conceptual task using a different framework:

CrewAI – role-based, multi-agent collaboration
LangChain + ReAct – tool-augmented reasoning with strict parsing
AutoGen – conversation-driven, turn-based agents

All implementations are executed sequentially within one .ipynb file to make comparison easier.

Key Learnings
**CrewAI**

Intuitive abstraction for multi-agent collaboration
Best suited for role-based workflows
Minimal control over low-level execution details

**LangChain (ReAct)**

Demonstrates classic Reason + Act behavior
Highly dependent on strict output formats
Local LLMs (e.g., LLaMA-3) may cause:
output parsing errors
infinite loops without safeguards
Requires explicit handling such as handle_parsing_errors=True

**AutoGen**

Conversation-first agent design
Strongly influenced by system_message
Requires explicit termination logic
Works well with local LLMs when properly guided

Why Local LLM?

All examples use a local LLM (LLaMA-3 via Ollama) instead of hosted APIs to:
    Avoid API costs and rate limits
    Ensure reproducibility
    Observe raw agent behavior without model-side guardrails
    Surface framework-level limitations clearly

How to Run?

Install dependencies
    pip install -r requirements.txt

Start Ollama and pull the model
    ollama serve
    ollama pull llama3

Open and run the notebook
    Execute cells top to bottom.

Purpose of This Practical

This notebook is not meant to showcase perfect outputs.
Instead, it intentionally highlights:
    framework design differences
    common pitfalls
    trade-offs when working with local LLMs
    why agent architecture matters more than model choice

Summary

This practical shows that:
There is no “one best” agent framework
Each framework optimizes for a different mental model
Understanding failure modes is as important as success cases
>>>>>>> bdc2cac (feat: add practical_00_agentic_frameworks comparing CrewAI, LangChain ReAct, and AutoGen)
