# Prototype-a-Vibe-Matcher-Notebook

#  Vibe Matcher — AI Vibe-Based Recommendation System  
> Mood → Embeddings → Vector Search → Top-3 Matches  
> *Search with feelings, not keywords.*

---

##  Project Overview

**Vibe Matcher** is an AI-powered mini recommendation system that returns fashion products based on the *vibe* the user describes.

Example:
> Query: `"energetic urban chic"`  
> Output: **Urban Bomber Jacket**, **Tailored Blazer**, **Vintage Tote Bag**

Instead of keyword search, we use:
1. **Embeddings** (OpenAI or TF-IDF fallback)
2. **Cosine Similarity**
3. Ranking top-3 matching products

 **Goal:** Demonstrate how embeddings + vector search power modern recommendation systems.

---

## Features

| Feature | Description |
|---------|-------------|
|  Converts user "vibe" query into vector embedding |
|  Calculates cosine similarity for Top-3 product matches |
|  Includes mock dataset (7 fashion products) |
|  Can run *offline* using TF-IDF embeddings |
|  Built-in evaluation + latency measurement |
|  Ready for Pinecone or Weaviate integration (production use) |

---

##  Tech Stack

| Component | Technology |
|----------|------------|
| Embeddings | OpenAI `text-embedding-ada-002` OR TF-IDF fallback |
| Data | Pandas (mock product dataset) |
| Similarity Search | sklearn cosine similarity |
| Notebook | Colab / Jupyter / VS Code |
| Visualization | Matplotlib |

---

 vibe-matcher

├── vibe_matcher_notebook.ipynb 

├── vibe_matcher_eval.csv 

├── vibe_matcher_latency.png

└── README.md 




##  How to Run (Quick Start)

### Install dependencies

pip install -r requirements.txt

vibe_matcher_notebook.ipynb

 Enable OpenAI Embeddings (optional, improves results)

Inside the notebook, add:

python

Copy code

from openai import OpenAI

client = OpenAI(api_key="YOUR_API_KEY Add here")

Embeddings call:

python

Copy code

client.embeddings.create(
    model="text-embedding-ada-002",
    input=text
)
If API key is not available, the notebook automatically falls back to TF-IDF mode.

 Output Results

 Top-3 Recommendations (example)
Query	Top Match	Similarity Score
energetic urban chic	Urban Bomber Jacket	0.612
cozy weekend at home	Cozy Knit Sweater	0.428
minimal night-out elegance	Sleek Slip Dress	0.491

 Latency Results
Latency graph saved as:

