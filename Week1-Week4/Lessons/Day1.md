# 📅 DAY 1: INSTALL OLLAMA

## 🎯 GOAL: Install Ollama and run your first AI model

---

## WHAT IS OLLAMA?

Ollama lets you run AI models on YOUR computer - FREE, no API costs, no internet needed after setup.

**Works on:** Windows, Mac, Linux

---

## 📥 INSTALL OLLAMA

### Linux / macOS
```bash
curl -fsSL https://ollama.com/install.sh | sh
```

### Windows
1. Go to https://ollama.com/download
2. Download the .exe installer
3. Run and install

### Android (Termux)
```bash
pkg install ollama
```

---

## ✅ VERIFY INSTALLATION

```bash
ollama --version
```

You should see: `ollama version x.x.x`

---

## 🤖 DOWNLOAD YOUR FIRST MODEL

### Light Models (2-4GB) - Fast on any PC
```bash
ollama pull qwen2.5:3b
ollama pull llama3.2:1b
```

### Medium Models (6-8GB) - Better quality
```bash
ollama pull llama3.2:3b
ollama pull qwen2.5:7b
```

### Heavy Models (10GB+) - Best quality
```bash
ollama pull llama3.2:11b
ollama pull qwen2.5:14b
```

**Recommended for beginners:** Start with `qwen2.5:3b` (2GB, fast!)

---

## 💬 TEST YOUR MODEL

```bash
ollama run qwen2.5:3b
```

Type: `Hello, how are you?`

Press `Ctrl + D` to exit

---

## 📝 EXERCISE

1. ✅ Install Ollama
2. ✅ Download `qwen2.5:3b` model
3. ✅ Run it and ask 3 questions
4. ✅ Take screenshot of conversation

---

## 🎉 CONGRATULATIONS!

You just ran a full AI model on YOUR computer!

---

## 📌 DAY 2 PREVIEW

Tomorrow: Learn basic commands and how to use models programmatically

---

## ❓ TROUBLESHOOTING

| Problem | Solution |
|---------|----------|
| "curl not found" | Install curl first |
| Slow download | Check internet connection |
| Out of memory | Use smaller model |
| Permission denied | Run with sudo (Linux) |

---

**Questions? Ask in community group! 💬**
