# 📅 DAY 7: LANGGRAPH FUNDAMENTALS

## 🎯 GOAL: Learn about stateful agent workflows

---

## 🤔 WHAT IS LANGGRAPH?

LangGraph is LangChain's tool for creating **agentic workflows** - AI systems that can:
- Make decisions
- Use tools
- Remember state
- Loop and iterate

---

## 🔄 STATE GRAPH BASICS

```python
from langgraph.graph import StateGraph, END
from langchain_ollama import ChatOllama
from typing import TypedDict, Annotated
import operator

# Define state
class AgentState(TypedDict):
    messages: list

# Initialize LLM
llm = ChatOllama(model="qwen2.5:3b", base_url="http://localhost:11434")

# Define node function
def chat_node(state):
    messages = state["messages"]
    response = llm.invoke(messages[-1]["content"])
    return {"messages": messages + [{"role": "assistant", "content": response}]}

# Create graph
workflow = StateGraph(AgentState)
workflow.add_node("chat", chat_node)
workflow.set_entry_point("chat")
workflow.add_edge("chat", END)

# Compile
app = workflow.compile()

# Run
result = app.invoke({
    "messages": [{"role": "user", "content": "Hello!"}]
})
print(result["messages"][-1]["content"])
```

---

## 🔀 BRANCHING WORKFLOWS

```python
from langgraph.graph import StateGraph, END
from typing import TypedDict

class RouterState(TypedDict):
    topic: str
    response: str

def router_node(state):
    topic = state["topic"].lower()
    
    if "code" in topic or "python" in topic:
        return {"response": "I'll help with your code!"}
    elif "math" in topic:
        return {"response": "Let me calculate this..."}
    else:
        return {"response": "Interesting question!"}

workflow = StateGraph(RouterState)
workflow.add_node("router", router_node)
workflow.set_entry_point("router")
workflow.add_edge("router", END)

app = workflow.compile()
result = app.invoke({"topic": "Python programming"})
print(result["response"])
```

---

## 📝 EXERCISE

1. Create a simple state graph
2. Add multiple nodes
3. Branch based on user input

---

## 🎉 CONGRATULATIONS!

You learned LangGraph basics!

---

## 📌 DAY 8 PREVIEW

Tomorrow: Tool Calling with LangGraph

---

**Questions? Community group! 💬**
