# 📅 DAY 3: YOUR FIRST AI APPLICATION

## 🎯 GOAL: Build a real AI application in Python

---

## 🏗️ BUILD: AI Chatbot

### Step 1: Create File
```python
# chatbot.py
from langchain_ollama import ChatOllama

def chat():
    llm = ChatOllama(
        model="qwen2.5:3b",
        base_url="http://localhost:11434"
    )
    
    print("🤖 AI Chatbot Ready! (type 'quit' to exit)")
    print("-" * 40)
    
    while True:
        user_input = input("You: ")
        if user_input.lower() == 'quit':
            break
        
        response = llm.invoke(user_input)
        print(f"AI: {response.content}")
        print()

if __name__ == "__main__":
    chat()
```

### Step 2: Run
```bash
python chatbot.py
```

### Step 3: Chat!

---

## 🎯 IMPROVE: Add System Prompt

```python
from langchain_ollama import ChatOllama
from langchain_core.messages import HumanMessage, SystemMessage

llm = ChatOllama(
    model="qwen2.5:3b",
    base_url="http://localhost:11434"
)

# System prompt - sets AI personality
messages = [
    SystemMessage(content="You are a helpful coding assistant."),
    HumanMessage(content="How do I learn Python?")
]

response = llm.invoke(messages)
print(response.content)
```

---

## 📝 EXERCISE

Build a chatbot that:
1. Has a personality (e.g., "You are a Python teacher")
2. Responds to user questions
3. Shows the conversation history

---

## 🎉 CONGRATULATIONS!

You just built your first AI application!

---

## 📌 DAY 4 PREVIEW

Tomorrow: Learn about Prompt Templates - make AI responses consistent

---

## 💡 EXTRA: API Chatbot

Want a web interface? Use Flask:

```python
from flask import Flask, request, jsonify
from langchain_ollama import ChatOllama

app = Flask(__name__)
llm = ChatOllama(model="qwen2.5:3b", base_url="http://localhost:11434")

@app.route('/chat', methods=['POST'])
def chat():
    data = request.json
    response = llm.invoke(data['message'])
    return jsonify({"response": response.content})

app.run(port=5000)
```

Run with:
```bash
pip install flask
python app.py
```

Then visit: http://localhost:5000/chat

---

**Questions? Ask in community! 💬**
