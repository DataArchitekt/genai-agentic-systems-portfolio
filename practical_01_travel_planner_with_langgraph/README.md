# 🌍 Agentic Travel Planner using LangGraph & Local LLMs

A stateful, agentic AI system that converts natural language travel requests into a multi-day travel plan using LangGraph and local LLMs.

## ✨ Why This Project Matters
-  Graph-based agent execution
-  Explicit state contracts
-  Dynamic routing across planning stages
-  Deterministic + probabilistic reasoning combined
-  Local-first LLM usage (no paid APIs)

## What does the Agent do?
Given a user’s travel request, the agent:
- Extracts structured intent using an LLM
- Normalizes and validates dates
- Computes derived trip state (days & nights)
- Routes dynamically through planning stages
- Produces a day-by-day itinerary

All steps operate on a shared, typed state, enforced by LangGraph.

## 🔄 Agent Flow
```mermaid
User Input
   ↓
process_input (LLM extraction)
   ↓
compute_trip_duration (derived state)
   ↓
Dynamic Routing (LangGraph)
   ├── search_flights
   ├── search_hotels
   ├── check_weather
   ├── find_attractions
   ├── create_itinerary
   ↓
Final Travel Plan
```

## Key Technical Concepts Demonstrated

### Agentic Design
- Stateful execution (not linear chains)
- Clear separation of:
    - Intent extraction
    - Derived computation
    - Planning & reasoning
- Failure-safe transitions

### LangGraph Best Practices
- Conditional routing with add_conditional_edges
- Explicit state schema (prevents silent key drops)
- Derived state created inside graph nodes
- Debugging via node-level state inspection

### LLM Usage
- Local inference via Ollama
- Structured output extraction (no brittle JSON parsing)
- Deterministic logic where LLMs are unnecessary

### 🛠️ Tech Stack
- Python 3.11
- LangGraph
- LangChain
- Ollama (local LLM runtime)
- LLaMA models
- TypedDict / Pydantic for state safety

### How to Run This Project
1. Install dependencies
pip install -r requirements.txt
2. Start Ollama (outside venv)
- ollama serve
- Pull a model if needed: ollama pull llama3
3. Run the notebook
Open and execute: Travel_planner_with_langgraph.ipynb
4. Example Input: I want to travel from London to Paris from June 15, 2024 to June 25, 2024.
I have a budget of $4000 for 2 people.
I'm interested in temples, food, and gardens.

### 🔮 Future Enhancements
- Real flight / hotel APIs
- Persistent user preferences
- Memory across sessions
- Retry & validation nodes
- Streamlit / FastAPI UI
- Conversion to a Python package