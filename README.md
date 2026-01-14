# RapidFire-AI-Winter-2025-RAG
This repository contains my submission for the RapidFire AI Winter 2025 Competition (RAG Track).
## Overview
- **Task:** Financial opinion question answering (retrieval-first RAG)
- **Dataset:** FiQA (BEIR benchmark)
- **Base generator:** Qwen2.5-0.5B-Instruct
- **Embeddings:** sentence-transformers/all-MiniLM-L6-v2
- **Retriever:** FAISS similarity search (top-k = 8)
- **Reranker:** ms-marco-MiniLM-L6-v2 (included; metrics evaluated pre-reranking)
- **Approach:** Systematic chunking and retrieval experimentation using RapidFire AI

## Experiment Focus
- **Chunk size:** 128, 256  
- **Chunk overlap:** 0, 16, 32  
- **Sampling:** Pilot run at 0.01; final experiments at 0.1 due to free-tier Colab memory constraints  
- **Metrics:** Precision, Recall, F1, NDCG@5, MRR  
- All runs completed fully; no early stopping was applied.

## Repository Structure
- `notebook/`: End-to-end Colab notebook  
- `artifacts/`: Results table and TensorBoard event files  
- `logs/`: Relevant RapidFire logs for this RAG experiment  
- `screenshots/`: Metric plots used in submission  

## How to Run
Open `notebook/rf_colab_rag_fiqa_submission.ipynb` in Google Colab and run all cells top-to-bottom.

(Optional) If dependency issues arise:
```bash
pip install -U langchain langchain-community langchain-core \
  langchain-huggingface sentence-transformers vllm "ray[default]" faiss-gpu-cu12
```
