# 📅 DAY 2: OLLAMA COMMANDS & PYTHON

## 🎯 GOAL: Learn Ollama commands and run AI from Python

---

## 🔧 OLLAMA COMMANDS

### Essential Commands
```bash
ollama serve        # Start Ollama server (runs in background)
ollama list         # Show all downloaded models
ollama pull <name>  # Download a new model
ollama rm <name>    # Remove a model
ollama run <name>   # Chat with a model
ollama show <name>  # Show model info
```

### List Models
```bash
ollama list
```

Output:
```
NAME                    ID           SIZE      MODIFIED
qwen2.5:3b              a4a8217...   2.0GB     2 days ago
llama3.2:1b             b7427c1...   1.3GB     3 days ago
```

### Model Info
```bash
ollama show qwen2.5:3b
```

---

## 🐍 USE OLLAMA IN PYTHON

### Install Library
```bash
pip install langchain langchain-ollama
```

### First Python Code
```python
from langchain_ollama import ChatOllama

# Connect to local Ollama
llm = ChatOllama(
    model="qwen2.5:3b",
    base_url="http://localhost:11434"
)

# Ask question
response = llm.invoke("What is Python?")
print(response.content)
```

Save as `hello_ai.py` and run:
```bash
python hello_ai.py
```

---

## 📊 OLLAMA API

### REST API
```bash
# Generate endpoint
curl http://localhost:11434/api/generate \
  -d '{"model":"qwen2.5:3b","prompt":"Hello"}'

# Chat endpoint
curl http://localhost:11434/api/chat \
  -d '{"model":"qwen2.5:3b","messages":[{"role":"user","content":"Hi"}]}'
```

---

## 📝 EXERCISE

1. ✅ Run `ollama list` - note your models
2. ✅ Run `ollama show qwen2.5:3b` - see model details
3. ✅ Create Python file with code above
4. ✅ Run it and print response

---

## 🎉 CONGRATULATIONS!

You can now:
- ✅ Use Ollama commands
- ✅ Run AI from Python
- ✅ Use Ollama API

---

## 📌 DAY 3 PREVIEW

Tomorrow: Build your first real AI application!

---

## 💡 PRO TIP

Models are stored at:
- Linux: `/usr/share/ollama/.ollama/models/`
- macOS: `~/.ollama/models/`
- Windows: `C:\Users\<you>\.ollama\models\`

---

**Questions? Community group! 💬**
