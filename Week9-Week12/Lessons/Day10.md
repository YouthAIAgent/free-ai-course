# 📅 DAY 10: RAG - RETRIEVAL AUGMENTED GENERATION

## 🎯 GOAL: Make AI answer questions from YOUR documents!

---

## 🤔 WHAT IS RAG?

RAG = Retrieval + Augmentation + Generation

Instead of only using training data, AI can now:
1. 📄 Load your documents
2. 🔍 Find relevant info
3. 🤖 Generate answer from that info

**Use cases:**
- Chat with your PDFs
- Q&A on your notes
- Company knowledge base

---

## 📚 SIMPLE RAG PIPELINE

```python
from langchain_ollama import ChatOllama, OllamaEmbeddings
from langchain_community.document_loaders import TextLoader
from langchain.text_splitter import RecursiveCharacterTextSplitter
from langchain_community.vectorstores import Chroma

# 1. Load documents
loader = TextLoader("my_notes.txt")
documents = loader.load()

# 2. Split into chunks
splitter = RecursiveCharacterTextSplitter(chunk_size=500, chunk_overlap=50)
chunks = splitter.split_documents(documents)

# 3. Create embeddings
embeddings = OllamaEmbeddings(model="nomic-embed-text", base_url="http://localhost:11434")

# 4. Create vector store
vectorstore = Chroma.from_documents(chunks, embeddings)

# 5. Create retriever
retriever = vectorstore.as_retriever(search_kwargs={"k": 2})

# 6. Create chain
llm = ChatOllama(model="qwen2.5:3b", base_url="http://localhost:11434")

# RAG Chain
from langchain_core.prompts import PromptTemplate
from langchain_core.runnables import RunnablePassthrough

template = """Based on the following context, answer the question:

Context: {context}

Question: {question}

Answer:"""

prompt = PromptTemplate.from_template(template)

chain = (
    {"context": retriever, "question": RunnablePassthrough()}
    | prompt
    | llm
)

# Ask question
result = chain.invoke("What is mentioned about Python?")
print(result.content)
```

---

## 📄 CREATE SAMPLE DOCUMENT

```bash
# Create a text file with your notes
cat > my_notes.txt << 'EOF'
Python Programming Notes
=======================

Python is a high-level programming language.
It was created by Guido van Rossum in 1991.

Key Features:
- Easy to learn syntax
- Interpreted language
- Dynamic typing
- Cross-platform

Common Uses:
- Web development
- Data science
- Machine learning
- Automation

Best for beginners!
EOF
```

---

## 📝 EXERCISE

1. Create a text file with your notes
2. Load it with TextLoader
3. Ask questions about your notes
4. Verify AI answers from your document

---

## 🎉 CONGRATULATIONS!

You learned RAG!

---

## 📌 NEXT STEPS

- Week 9-12: Build full RAG projects
- Use PDF loaders for real documents
- Deploy as web app

---

**Questions? Community group! 💬**
