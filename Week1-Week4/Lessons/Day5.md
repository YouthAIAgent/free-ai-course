# 📅 DAY 5: CONVERSATION MEMORY

## 🎯 GOAL: Make AI remember previous messages

---

## 🤔 WHY MEMORY?

Without memory, AI forgets everything after each response. 
With memory, AI remembers the whole conversation!

---

## 🧠 MEMORY TYPES

### 1. Buffer Memory (Simple)
```python
from langchain_ollama import ChatOllama
from langchain_core.chat_history import InMemoryChatMessageHistory
from langchain_core.runnables.history import RunnableWithMessageHistory

llm = ChatOllama(model="qwen2.5:3b", base_url="http://localhost:11434")

# Memory store
store = {}

def get_history(session_id):
    if session_id not in store:
        store[session_id] = InMemoryChatMessageHistory()
    return store[session_id]

# Chain with memory
chain = RunnableWithMessageHistory(
    llm,
    get_history,
    input_messages_key="input",
    history_messages_key="history"
)

# Chat
response = chain.invoke(
    {"input": "My name is Raj"},
    config={"configurable": {"session_id": "user123"}}
)
print(response.content)

# AI remembers!
response = chain.invoke(
    {"input": "What is my name?"},
    config={"configurable": {"session_id": "user123"}}
)
print(response.content)  # Will say "Raj"!
```

---

## 💾 PERSISTENT MEMORY (Save to File)

```python
import json
from datetime import datetime

class FileChatHistory:
    def __init__(self, filename="chat_history.json"):
        self.filename = filename
        self.messages = self.load()
    
    def load(self):
        try:
            with open(self.filename, 'r') as f:
                return json.load(f)
        except:
            return []
    
    def save(self):
        with open(self.filename, 'w') as f:
            json.dump(self.messages, f, indent=2)
    
    def add_user(self, message):
        self.messages.append({"role": "user", "content": message, "time": str(datetime.now())})
        self.save()
    
    def add_ai(self, message):
        self.messages.append({"role": "ai", "content": message, "time": str(datetime.now())})
        self.save()
    
    def get_messages(self):
        return self.messages

# Use it
history = FileChatHistory("my_chat.json")
history.add_user("Hello!")
history.add_ai("Hi! How can I help you?")
print(history.get_messages())
```

---

## 📝 EXERCISE

1. Create a chatbot with InMemoryChatMessageHistory
2. Ask something, then ask a follow-up question
3. Verify AI remembers

---

## 🎉 CONGRATULATIONS!

You learned Memory!

---

## 📌 DAY 6 PREVIEW

Tomorrow: Build a Personal AI Assistant Project

---

**Questions? Community group! 💬**
