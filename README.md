# BERTopic-Based Topic Modeling with Interactive UI

This repository presents an implementation of the paper  
**[BERTopic: Neural Topic Modeling with Class-based TF-IDF](https://arxiv.org/abs/2203.05794)**  
by *Maarten Grootendorst (2022)*, built into a single Python script with an interactive interface for exploring topics in textual data.

The implementation demonstrates the core ideas from the paper using a real-world dataset (iPhone product reviews), and includes both BERTopic and LDA for comparative purposes, along with interactive UI elements for visual inspection of topic quality.

---

## Paper Summary

**BERTopic** is a topic modeling technique that combines:
- **Transformer-based embeddings** (e.g., BERT) to capture semantic information
- **UMAP** for dimensionality reduction
- **HDBSCAN** for flexible density-based clustering
- **Class-based TF-IDF (c-TF-IDF)** for extracting interpretable topic keywords

Key innovations in the paper:
- Models semantic similarity more effectively than traditional models like LDA
- Handles **dynamic topic reduction** (e.g., merging similar topics)
- Scales to large corpora using transformer sentence embeddings

> Paper: [BERTopic: Neural Topic Modeling with Class-based TF-IDF (arXiv:2203.05794)](https://arxiv.org/abs/2203.05794)

---

## What This Implementation Includes

This project re-implements BERTopic’s end-to-end logic in a single script with additional practical features for analysis and comparison:

### Core BERTopic Pipeline (from the paper)
- Text preprocessing with `spaCy` (lemmatization, stopword removal)
- Embedding using `sentence-transformers` (`all-MiniLM-L6-v2`)
- Dimensionality reduction via `UMAP`
- Clustering via `HDBSCAN`
- Topic representation via **c-TF-IDF**
- Topic probability estimation (`calculate_probabilities=True`)

### Additions & Enhancements
- **Topic Coherence (TC)**: Cosine similarity among keyword embeddings
- **Topic Diversity (TD)**: Uniqueness of keywords across topics
- **WordClouds** for each topic
- **LDA Model** implementation using `sklearn` for comparison
- **Interactive UI** using `ipywidgets`:
  - Dropdown to explore keywords
  - Shows 5 example reviews from the matched topic
  - WordCloud visualization for selected topic

---