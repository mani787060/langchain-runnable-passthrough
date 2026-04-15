# LangChain RunnablePassthrough Mastery
[![LangChain](https://img.shields.io/badge/Framework-LangChain-green)](https://www.langchain.com/)
[![Python](https://img.shields.io/badge/Python-3.9%2B-blue)](https://www.python.org/)
[![RAG](https://img.shields.io/badge/Architecture-RAG-orange)](https://python.langchain.com/docs/use_cases/question_answering/)

## 🏗️ Project Overview
This repository explores **`RunnablePassthrough`**, one of the most critical routing components in the LangChain Expression Language (LCEL). In complex pipelines—especially Retrieval-Augmented Generation (RAG)—you frequently need to execute a function (like a database search) but *also* keep the original user input to pass to the next step. This project demonstrates how to forward data unchanged and how to seamlessly inject new data into the chain's state.

---

## 🛠️ Key Technical Implementations

### 1. State Preservation (The Passthrough)
* **Identity Function:** Using `RunnablePassthrough()` to act as a transparent pipe, ensuring that upstream data (like a user's raw question) reaches downstream components (like the final prompt template) without being overwritten.

### 2. Context Augmentation (The Assign Method)
* **`RunnablePassthrough.assign()`:** Demonstrating the industry-standard method for adding new keys to an input dictionary on the fly. 
* **Dynamic Injection:** Showing how to take an input like `{"question": "What is LCEL?"}`, run a retrieval function, and output `{"question": "What is LCEL?", "context": "..."}` in a single, readable line of code.

### 3. The RAG Backbone
* **Simulated Retrieval:** Building a foundational RAG data flow: `{"context": retriever, "question": RunnablePassthrough()} | Prompt | Model`. This proves an understanding of how external knowledge is integrated into generative AI.

---

## 💻 Tech Stack
* **Language:** Python 3.9+
* **Orchestration:** LangChain (`langchain-core`, `langchain-google-genai`)
* **Model:** Google Gemini Pro
* **Environment:** `python-dotenv`

---

## 🚀 Getting Started

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/your-username/langchain-runnable-passthrough-rag.git](https://github.com/your-username/langchain-runnable-passthrough-rag.git)

2. **Install Dependencies:**
   ```bash
   pip install -U langchain-core langchain-google-genai python-dotenv

3. **Setup API Key:**
   Create a .env file in the root directory:
   ```bash
   GOOGLE_API_KEY=your_gemini_key_here

4. **Run the Implementation:**
   ```bash
   python runnable_passthrough.py   
