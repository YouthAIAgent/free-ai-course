# 📅 DAY 4: PROMPT TEMPLATES

## 🎯 GOAL: Learn to create reusable prompts

---

## 📝 WHAT IS A PROMPT TEMPLATE?

A prompt template is a reusable format for your prompts. Instead of writing full prompts each time, you create a template with variables.

---

## 🔧 CREATE PROMPT TEMPLATE

```python
from langchain_ollama import ChatOllama
from langchain_core.prompts import PromptTemplate

llm = ChatOllama(model="qwen2.5:3b", base_url="http://localhost:11434")

# Create template
template = PromptTemplate(
    input_variables=["topic"],
    template="Explain {topic} in simple terms for a beginner."
)

# Use template
prompt = template.invoke({"topic": "Python programming"})
response = llm.invoke(prompt)
print(response.content)
```

---

## 🔄 CHAIN: Template + LLM

```python
from langchain_ollama import ChatOllama
from langchain_core.prompts import PromptTemplate

llm = ChatOllama(model="qwen2.5:3b", base_url="http://localhost:11434")

# Create chain
template = PromptTemplate(
    input_variables=["topic", "level"],
    template="Explain {topic} for a {level} developer."
)

chain = template | llm

# Use chain
response = chain.invoke({"topic": "Python", "level": "beginner"})
print(response.content)
```

---

## 📚 CHAT PROMPT TEMPLATE

```python
from langchain_ollama import ChatOllama
from langchain_core.prompts import ChatPromptTemplate

llm = ChatOllama(model="qwen2.5:3b", base_url="http://localhost:11434")

# Chat template
template = ChatPromptTemplate.from_messages([
    ("system", "You are a {role} assistant."),
    ("human", "Help me with {task}.")
])

chain = template | llm

response = chain.invoke({
    "role": "Python teacher",
    "task": "learning programming"
})
print(response.content)
```

---

## 📝 EXERCISE

Create a prompt template for:
1. Code review assistant
2. Translation tool
3. Recipe generator

---

## 🎉 CONGRATULATIONS!

You learned Prompt Templates!

---

## 📌 DAY 5 PREVIEW

Tomorrow: Memory - Make AI remember conversations

---

**Questions? Community group! 💬**
