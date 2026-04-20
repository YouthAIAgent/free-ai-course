# 📅 DAY 9: MULTI-AGENT SYSTEMS

## 🎯 GOAL: Create multiple AI agents that work together!

---

## 🤖 WHAT IS MULTI-AGENT?

Multiple AI agents, each with their own role, working together like a team.

Example:
- **Researcher Agent** - Finds information
- **Writer Agent** - Writes content
- **Editor Agent** - Reviews and edits

---

## 🏗️ BUILD: RESEARCH CREW

```python
from langchain_ollama import ChatOllama
from langchain_core.messages import HumanMessage

# Initialize LLM
llm = ChatOllama(model="qwen2.5:3b", base_url="http://localhost:11434")

# Agent 1: Researcher
researcher_prompt = """You are a researcher. 
Find information about: {topic}
Return key findings in bullet points."""

# Agent 2: Writer
writer_prompt = """You are a content writer.
Using this research: {research}
Write a short 3-paragraph article."""

# Agent 3: Editor
editor_prompt = """You are an editor.
Review this article: {article}
Suggest improvements."""

def research_crew(topic):
    # Step 1: Research
    research = llm.invoke(researcher_prompt.format(topic=topic))
    
    # Step 2: Write
    article = llm.invoke(writer_prompt.format(research=research.content))
    
    # Step 3: Edit
    final = llm.invoke(editor_prompt.format(article=article.content))
    
    return final.content

# Run
result = research_crew("AI in Education")
print(result)
```

---

## ⚡ SIMPLE MULTI-AGENT WITH CREWAI

```python
# Install: pip install crewai
from crewai import Agent, Task, Crew

# Create agents
researcher = Agent(
    role="Researcher",
    goal="Find accurate information",
    backstory="Expert researcher with 10 years experience"
)

writer = Agent(
    role="Writer",
    goal="Write engaging content",
    backstory="Professional content writer"
)

# Create tasks
task1 = Task(
    description="Research latest AI trends",
    agent=researcher
)

task2 = Task(
    description="Write article about AI trends",
    agent=writer
)

# Run crew
crew = Crew(agents=[researcher, writer], tasks=[task1, task2])
result = crew.kickoff()
print(result)
```

---

## 📝 EXERCISE

1. Create 2 agents: one for math, one for science
2. Have them work together on a topic
3. Display the final result

---

## 🎉 CONGRATULATIONS!

You learned Multi-Agent Systems!

---

## 📌 DAY 10 PREVIEW

Tomorrow: RAG - Retrieval Augmented Generation

---

**Questions? Community group! 💬**
