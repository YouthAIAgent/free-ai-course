# 📅 DAY 6: YOUR FIRST PROJECT - PERSONAL AI ASSISTANT

## 🎯 GOAL: Build a complete AI Assistant with memory!

---

## 📋 PROJECT: PERSONAL AI ASSISTANT

### Features:
- 💬 Chat with AI
- 🧠 Remembers conversations
- 💾 Saves chat history
- 🎨 Clean interface

---

## 🛠️ PROJECT CODE

```python
# personal_ai_assistant.py

import os
import json
from datetime import datetime
from langchain_ollama import ChatOllama

class PersonalAIAssistant:
    def __init__(self, name="AI Assistant"):
        self.name = name
        self.model = "qwen2.5:3b"
        self.url = "http://localhost:11434"
        self.history_file = "chat_history.json"
        
        # Initialize LLM
        self.llm = ChatOllama(
            model=self.model,
            base_url=self.url
        )
        
        # Load history
        self.messages = self.load_history()
        
    def load_history(self):
        if os.path.exists(self.history_file):
            with open(self.history_file, 'r') as f:
                return json.load(f)
        return []
    
    def save_history(self):
        with open(self.history_file, 'w') as f:
            json.dump(self.messages, f, indent=2)
    
    def chat(self, user_input):
        # Add user message
        self.messages.append({
            "role": "user",
            "content": user_input,
            "time": str(datetime.now())
        })
        
        # Get AI response
        response = self.llm.invoke(user_input)
        
        # Add AI response
        self.messages.append({
            "role": "assistant",
            "content": response.content,
            "time": str(datetime.now())
        })
        
        # Save
        self.save_history()
        
        return response.content
    
    def print_history(self):
        print("\n" + "="*50)
        print("CHAT HISTORY")
        print("="*50)
        for msg in self.messages[-10:]:  # Last 10 messages
            role = "You" if msg["role"] == "user" else self.name
            print(f"\n{role}: {msg['content'][:100]}...")
    
    def run(self):
        print("\n" + "="*50)
        print(f"🤖 {self.name} - Type 'quit' to exit")
        print("="*50)
        
        while True:
            user_input = input("\nYou: ")
            if user_input.lower() == 'quit':
                print(f"\n👋 Bye! Chat saved to {self.history_file}")
                break
            
            if user_input.lower() == 'history':
                self.print_history()
                continue
            
            response = self.chat(user_input)
            print(f"\n{self.name}: {response}")

if __name__ == "__main__":
    assistant = PersonalAIAssistant("Friday")
    assistant.run()
```

---

## 🚀 RUN THE PROJECT

```bash
python personal_ai_assistant.py
```

---

## 📝 EXERCISE

1. ✅ Run the code
2. ✅ Chat with AI
3. ✅ Type 'history' to see past conversations
4. ✅ Restart and verify AI remembers
5. ✅ Customize with your name

---

## 🎉 CONGRATULATIONS!

You built your first AI project!

---

## 📌 DAY 7-10 PREVIEW

Next lessons: Improve your assistant with more features!

---

**Questions? Ask in community! 💬**
