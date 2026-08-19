# Hate Speech Detection in Portuguese: From Traditional ML to Local LLMs

## Project Overview
This project tackles the classification of offensive language in Brazilian Portuguese Instagram comments using the HateBR dataset. It compares three distinct natural language processing paradigms to understand the trade-offs between computational cost, rule-based logic, and contextual understanding. The project evolves from classical Machine Learning representations to the orchestration of Local Large Language Models (LLMs).

## Main Objectives
* **Baseline Comparison:** Evaluate traditional text representations (TF-IDF vs. GloVe) combined with engineered linguistic features using algorithms like Logistic Regression, SVM, and Random Forest.
* **LLM Orchestration:** Deploy open-source LLMs (Llama 3.2 3B and Qwen 2.5 7B-Instruct) locally using Ollama and LangChain.
* **Prompt Engineering:** Optimize prompts using Zero-shot, Few-shot, and Chain of Thought (CoT) techniques to maximize accuracy while minimizing inference time and "Parse Error Rates" (model censorship).

## Technologies & Tools
* **Language:** Python
* **Traditional ML:** scikit-learn (SVM, Random Forest, Logistic Regression), spaCy (Linguistic Features), TF-IDF, GloVe Word Embeddings.
* **LLM Stack:** Ollama (Local deployment), LangChain (Prompt orchestration).

## Key Insights & Conclusions
* **Semantic vs. Lexical (ML Phase):** The GloVe + Linear SVM model (F1: 0.816) outperformed TF-IDF, proving that semantic representation combined with engineered linguistic features handles toxicity better than exact word frequencies.
* **The "Safety vs. Utility" Dilemma:** Llama 3.2 (3B) proved too strictly aligned for this task, returning a 44% Parse Error Rate in Zero-shot settings as its safety filters refused to process offensive words 
* **The Winning Architecture:** Qwen 2.5 (7B-Instruct) utilizing a Chain of Thought + Few-shot prompt achieved the highest performance (F1: 0.880). While rule-based systems and ML soften toxicity or miss implicit hate, the LLM successfully understood sarcasm, irony, and colloquial contexts without triggering censorship filters.