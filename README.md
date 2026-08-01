# 🏥 Medical Q&A RAG System

A Retrieval-Augmented Generation (RAG) pipeline that answers medical questions about heart disease, diabetes, blood pressure, and cholesterol — built with LangChain, ChromaDB, and Groq LLaMA3.

This project extends the [MedBuddy](https://github.com/Arpita7007/ml-17-1-med-buddy-ml) heart disease predictor with a conversational layer, allowing users to ask follow-up medical questions in plain language and receive grounded, source-backed answers.

---

## 🧠 How It Works

```
User Question
     ↓
Query Embedding (HuggingFace all-MiniLM-L6-v2)
     ↓
Similarity Search (ChromaDB — Top 3 chunks)
     ↓
Retrieved Context + Question → Prompt
     ↓
LLM (Groq LLaMA 3.1 8B Instant)
     ↓
Answer + Source
```

---

## 🛠️ Tech Stack

| Component        | Tool                              |
|-----------------|-----------------------------------|
| Framework        | LangChain 0.2.16                 |
| Embeddings       | HuggingFace all-MiniLM-L6-v2    |
| Vector Database  | ChromaDB                         |
| LLM              | Groq LLaMA 3.1 8B Instant (free) |
| Data             | ChatDoctor / HealthCareMagic-100k |
| Language         | Python 3.11                      |

---

## 📁 Project Structure

```
├── Medical_QA_RAG.ipynb       # Main RAG pipeline notebook
├── medical_qa_data.txt        # Filtered medical Q&A dataset (500 records)
└── README.md
```

---

## 🚀 Getting Started

### 1. Clone the repo
```bash
git clone https://github.com/Arpita7007/medical-qa-rag.git
cd medical-qa-rag
```

### 2. Install dependencies
```bash
pip install langchain==0.2.16 langchain-community==0.2.16 langchain-groq==0.1.9 \
            langchain-text-splitters==0.2.4 sentence-transformers chromadb tiktoken
```

### 3. Set your Groq API key
Get a free key at [console.groq.com](https://console.groq.com) and set it as an environment variable:
```bash
# Windows
set GROQ_API_KEY=your_key_here

# Mac/Linux
export GROQ_API_KEY=your_key_here
```

### 4. Run the notebook
Open `Medical_QA_RAG.ipynb` in Jupyter or VS Code and run all cells.

---

## 💬 Example Outputs

**Q: What causes high blood pressure?**
> High blood pressure can be caused by various factors including psychological stress, physical activity, and underlying medical conditions. It is recommended to monitor blood pressure frequently and consult a physician to investigate possible underlying causes.

**Q: What are the symptoms of a heart attack?**
> Common symptoms include chest pain or discomfort, shortness of breath, pain radiating to the arm or jaw, nausea, and cold sweats. Immediate medical attention is critical if these symptoms occur.

**Q: How do I manage type 2 diabetes?**
> Type 2 diabetes management includes regular blood sugar monitoring, a balanced low-glycemic diet, physical activity, medication as prescribed, and regular check-ups with a healthcare provider.

---

## 📊 Dataset

- **Source:** [ChatDoctor / HealthCareMagic-100k](https://huggingface.co/datasets/lavita/ChatDoctor-HealthCareMagic-100k) via HuggingFace
- **Size:** 500 filtered Q&A pairs
- **Topics:** Heart disease, diabetes, blood pressure, cholesterol
- **Format:** Patient question + Doctor answer pairs

---

## 🔗 Related Projects

- [MedBuddy — Heart Disease Predictor](https://github.com/Arpita7007/ml-17-1-med-buddy-ml) — The ML classifier this RAG system extends
- [Multi-Disease Predictor](https://github.com/Arpita7007/ML-Multi-Disease-Predictor) — Diabetes + heart disease prediction web app

---

## ⚠️ Disclaimer

This project is for educational purposes only. It is not a substitute for professional medical advice, diagnosis, or treatment.
