# 🎓 Free AI Engineer Course

[![GitHub stars](https://img.shields.io/github/stars/YouthAIAgent/free-ai-course?style=social)](https://github.com/YouthAIAgent/free-ai-course/stargazers)
[![GitHub forks](https://img.shields.io/github/forks/YouthAIAgent/free-ai-course?style=social)](https://github.com/YouthAIAgent/free-ai-course/network)
[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Course Duration](https://img.shields.io/badge/Duration-12%20Weeks-green.svg)](README.md)
[![Level](https://img.shields.io/badge/Level-Beginner%20to%20Intermediate-orange.svg)](README.md)
[![Cost](https://img.shields.io/badge/Cost-100%25%20FREE-red.svg)](README.md)

**Zero to AI Engineer in 12 Weeks | 100% Free | Build on Any Device**

---

<div align="center">

| 🕐 Duration | 💰 Cost | 🖥️ Requirement | 📚 Lessons | 🏆 Projects |
|:----------:|:------:|:---------------:|:----------:|:-----------:|
| 12 Weeks | FREE | 8GB+ RAM | 36+ | 3 |

</div>

---

## 🎯 What You'll Build

| Week | Project | Skills |
|:----:|---------|--------|
| **4** | 🤖 Personal AI Chatbot with Memory | LangChain, Memory |
| **8** | 🔍 Research Agent with Tools | LangGraph, Tool Calling |
| **12** | 📚 Document Q&A System + Certificate | RAG, LlamaIndex |

---

## 🚀 How to Use This Course (Simple Guide)

### 📖 How to Follow:

**This is a documentation course - just READ and LEARN!**

#### Step 1: Open README
Go to [`README.md`](README.md) on GitHub or download this folder

#### Step 2: Start with Day 1
Open [`Week1-Week4/Lessons/Day1.md`](Week1-Week4/Lessons/Day1.md)

#### Step 3: Follow Each Day
- Read the lesson
- Practice code on YOUR computer (optional)
- Complete the exercise

---

### 💻 Optional: Run Code on Your PC

If you want to try the examples:

```bash
# 1. Install Ollama
curl -fsSL https://ollama.com/install.sh | sh

# 2. Download model
ollama pull qwen2.5:3b

# 3. Install Python (Windows: python.com/download)

# 4. Install LangChain
pip install langchain langchain-ollama

# 5. Run example
python example.py
```

**But you can also just READ without running anything!**

---

### 📱 Read on Any Device:

| Device | Method |
|--------|--------|
| Phone 📱 | GitHub mobile app |
| PC 💻 | GitHub website |
| Offline 🌐 | Download as ZIP |

---

### 🎯 Quick:

```
DON'T: npm install, localhost, python server
DO: Read README → Follow Days → Practice
```

---

## 📋 Course Structure

```
📅 12 Weeks | 36 Lessons | 3 Projects | 1 Certificate
```

### 🔵 Phase 1: LLM Foundation (Week 1-4)
| Day | Topic | File |
|:---:|-------|------|
| 1 | Install Ollama | [`Day1.md`](Week1-Week4/Lessons/Day1.md) |
| 2 | Commands + Python | [`Day2.md`](Week1-Week4/Lessons/Day2.md) |
| 3 | First AI Application | [`Day3.md`](Week1-Week4/Lessons/Day3.md) |
| 4 | Prompt Templates | [`Day4.md`](Week1-Week4/Lessons/Day4.md) |
| 5 | Conversation Memory | [`Day5.md`](Week1-Week4/Lessons/Day5.md) |
| 6-7 | Personal AI Project | [`Project1.md`](Week1-Week4/Projects/Project1.md) |

### 🟢 Phase 2: Agentic AI (Week 5-8)
| Day | Topic | File |
|:---:|-------|------|
| 8 | LangGraph Fundamentals | [`Day8.md`](Week5-Week8/Lessons/Day8.md) |
| 9 | Tool Calling | [`Day9.md`](Week5-Week8/Lessons/Day9.md) |
| 10 | Multi-Agent Systems | [`Day10.md`](Week5-Week8/Lessons/Day10.md) |

### 🟡 Phase 3: RAG + Production (Week 9-12)
| Day | Topic | File |
|:---:|-------|------|
| 10 | RAG Basics | [`Day10.md`](Week9-Week12/Lessons/Day10.md) |

---

## 🛠️ Installation Commands

| Package | Command | Docs |
|--------|---------|------|
| **Ollama** | `curl -fsSL https://ollama.com/install.sh \| sh` | [Docs](https://ollama.com/docs) |
| **LangChain** | `pip install langchain langchain-ollama` | [Docs](https://python.langchain.com) |
| **LangGraph** | `pip install langgraph` | [Docs](https://langchain-ai.github.io/langgraph/) |
| **LlamaIndex** | `pip install llama-index` | [Docs](https://docs.llamaindex.ai) |
| **CrewAI** | `pip install crewai` | [Docs](https://docs.crewai.com) |

---

## 🔗 Free LLM APIs (No Credit Card!)

> Permanent free tiers for text inference. Use these APIs instead of or alongside Ollama!

| Provider | Free Tier | Models | Sign Up |
|---------|-----------|--------|---------|
| **Cohere** | 1,000 calls/month | Command R7, Embeddings | [Get Key](https://dashboard.cohere.com/api-keys) |
| **Google Gemini** | 10 RPM | Gemini 2.5 Flash | [Get Key](https://aistudio.google.com/app/apikey) |
| **Mistral AI** | ~1B tokens/month | Mistral Large, Codestral | [Get Key](https://console.mistral.ai/api-keys) |
| **Z AI (GLM)** | Permanent free | GLM-4.7-Flash | [Get Key](https://open.bigmodel.cn/usercenter/apikeys) |
| **Cerebras** | 1M tokens/day | Llama 3.1, Qwen 3 | [Get Key](https://cloud.cerebras.ai/) |
| **Cloudflare Workers AI** | 10K neurons/day | 50+ models | [Get Key](https://dash.cloudflare.com/) |

### Quick Example with Google Gemini:

```python
from langchain_ollama import ChatOllama

# Use free Gemini API
llm = ChatOllama(
    model="gemini-2.0-flash",
    base_url="https://generativelanguage.googleapis.com/v1beta"
)
# Note: Gemini requires API key in base_url
```

---

## 🔗 Free Resources & Repositories

| # | Repository | Stars | Purpose |
|:-:|-----------|:-----:|---------|
| 1 | [LangChain](https://github.com/langchain-ai/langchain) | 55k ⭐ | LLM App Framework |
| 2 | [LangGraph](https://github.com/langchain-ai/langgraph) | 15k ⭐ | Agentic Workflows |
| 3 | [LlamaIndex](https://github.com/run-llama/llama_index) | 30k ⭐ | RAG Framework |
| 4 | [Ollama](https://github.com/ollama/ollama) | 95k ⭐ | Local LLMs |
| 5 | [CrewAI](https://github.com/crewAIInc/crewAI) | 22k ⭐ | Multi-Agent |
| 6 | [Qdrant](https://github.com/qdrant/qdrant) | 25k ⭐ | Vector Database |
| 7 | [Ragas](https://github.com/explodinggradients/ragas) | 8k ⭐ | RAG Evaluation |
| 8 | [Awesome MCP](https://github.com/punkpeye/awesome-mcp-servers) | 12k ⭐ | MCP Servers |
| 9 | [Awesome LLM Apps](https://github.com/Shubhamsaboo/awesome-llm-apps) | 18k ⭐ | Templates |
| 10 | [AI Agents Beginners](https://github.com/microsoft/ai-agents-for-beginners) | 15k ⭐ | Curriculum |
| 11 | [Awesome Free LLM APIs](https://github.com/mnfst/awesome-free-llm-apis) | 5k ⭐ | Free API Keys |

---

## 💰 Cost Breakdown

| Component | Cost | Why Free? |
|-----------|:----:|-----------|
| Python | ₹0 | Open Source |
| Ollama | ₹0 | Local models |
| LangChain | ₹0 | Apache 2.0 |
| LangGraph | ₹0 | MIT License |
| LlamaIndex | ₹0 | MIT License |
| Models | ₹0 | Ollama Hub |
| **Total** | **₹0** | **100% Free!** |

---

## 🖥️ System Requirements

| Component | Minimum | Recommended |
|-----------|:-------:|:-----------:|
| RAM | 8 GB | 16 GB |
| Storage | 20 GB | 50 GB |
| OS | Ubuntu 20.04 / Win 10 / macOS 12 | Any |
| Internet | Only for setup | Not required |

---

## 🎓 Certificate

After completing Week 12 project:

1. ✅ Build a complete project
2. ✅ Push to your GitHub
3. ✅ Submit project link
4. 🎉 Get **FREE Certificate!**

---

## 💬 Community

[![Telegram](https://img.shields.io/badge/Telegram-Join-2CA5E0?style=flat&logo=telegram)](https://t.me/)
[![Discord](https://img.shields.io/badge/Discord-Join-5865F2?style=flat&logo=discord)](https://discord.gg/)
[![GitHub Issues](https://img.shields.io/badge/GitHub-Ask-181717?style=flat&logo=github)](https://github.com/YouthAIAgent/free-ai-course/issues)

**Need Help?** Open an issue or join our community!

---

## 📈 Learning Path

```
WEEK 1-4          WEEK 5-8           WEEK 9-12
─────────         ─────────          ─────────
Ollama            LangGraph          RAG Systems
LangChain         Tool Calling       LlamaIndex
Memory            Multi-Agent        Production
   ↓                 ↓                  ↓
Project 1        Project 2          Project 3
Chatbot          Research Agent     Document Q&A
```

---

## ✅ Prerequisites

- **None!** This course starts from scratch
- Basic computer knowledge
- Willingness to learn
- 8GB+ RAM computer

---

## 📖 How to Use This Course

1. **Start with Day 1** - Follow each lesson sequentially
2. **Practice daily** - 1-2 hours per day
3. **Build projects** - Apply what you learn
4. **Ask questions** - Use community support
5. **Complete all 3 projects** - Get certificate

---

## 🏆 Top Contributors

[![Contributors](https://img.shields.io/github/contributors/YouthAIAgent/free-ai-course)](https://github.com/YouthAIAgent/free-ai-course/graphs/contributors)

---

## 📝 License

[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

This course is **100% free** for everyone. Use it, share it, build on it!

---

<div align="center">

**⭐ Star this repo if you found it helpful!**

Made with ❤️ for the community

</div>
