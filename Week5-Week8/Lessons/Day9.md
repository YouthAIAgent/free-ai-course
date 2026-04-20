# 📅 DAY 8: TOOL CALLING WITH LANGGRAPH

## 🎯 GOAL: Give your AI agent tools to use!

---

## 🛠️ WHAT ARE TOOLS?

Tools let AI do things - search web, run code, read files, etc.

---

## 🔧 CREATE YOUR FIRST TOOL

```python
from langchain_core.tools import tool
from langgraph.prebuilt import create_react_agent
from langchain_ollama import ChatOllama

# Define tool
@tool
def calculator(expression: str) -> str:
    """Evaluate a math expression"""
    try:
        result = eval(expression)
        return f"Result: {result}"
    except:
        return "Error in calculation"

@tool
def get_time() -> str:
    """Get current time"""
    from datetime import datetime
    return datetime.now().strftime("%H:%M:%S")

# Initialize LLM
llm = ChatOllama(
    model="qwen2.5:3b",
    base_url="http://localhost:11434"
)

# Create agent with tools
agent = create_react_agent(llm, [calculator, get_time])

# Run agent
response = agent.invoke({
    "messages": [{"role": "user", "content": "What is 25 * 17?"}]
})
print(response["messages"][-1]["content"])
```

---

## 🔍 WEB SEARCH TOOL

```python
from langchain_ollama import ChatOllama
from langchain_community.tools import DuckDuckGoSearchRun

# Search tool
search = DuckDuckGoSearchRun()

# Define tool
@tool
def web_search(query: str) -> str:
    """Search the web for information"""
    return search.run(query)

# Use in agent
llm = ChatOllama(model="qwen2.5:3b", base_url="http://localhost:11434")

agent = create_react_agent(llm, [web_search])

response = agent.invoke({
    "messages": [{"role": "user", "content": "What is the capital of France?"}]
})
print(response["messages"][-1]["content"])
```

---

## 📝 EXERCISE

1. Create a calculator tool
2. Create a tool that returns your name
3. Create an agent that uses both

---

## 🎉 CONGRATULATIONS!

Your AI can now use tools!

---

## 📌 DAY 9 PREVIEW

Tomorrow: Multi-Agent Systems

---

**Questions? Community group! 💬**
