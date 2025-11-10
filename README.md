# Vibe Matcher: AI-Powered Fashion Recommendation System

A semantic search system that matches natural language vibe queries to fashion products using GPT-4o, sentence transformers, and FAISS.

## Why This Project?

I've been wanting to dive deeper into AI applications beyond tutorials, and Nexora's vision of bringing AI into fashion immediately caught my attention. The idea of helping people find clothes that match their *vibe*, not just keywords, is genuinely interesting—it's where useful technology meets a real everyday problem.

Plus, I'd actually use this. Figuring out what to wear or buy online is frustrating when traditional search only understands exact words. A system where you can type "something cozy for a weekend at home" and get relevant results? That's the kind of practical AI I want to build.

## Overview

Simple but effective pipeline:
- **GPT-4o** generates rich product descriptions
- **Sentence Transformers** create semantic embeddings (all-mpnet-base-v2)
- **FAISS** enables fast vector similarity search
- **Cosine Similarity** ranks top-3 matches

## Features

- Natural language vibe queries (e.g., "energetic urban chic for night out")
- Clean error handling and edge case management
- Performance metrics and visualizations
- Interactive query demo

## Quick Start

### Prerequisites
- Python 3.8+
- OpenAI API key

### Run It

1. **Clone & open:**
```bash
git clone https://github.com/AddyB0t/assignment.git
cd assignment
jupyter notebook vibe_matcher.ipynb
```

2. **Run the first cell** - auto-installs dependencies:
```python
!pip install -q openai pandas sentence-transformers faiss-cpu matplotlib numpy
```

3. **Set your API key** in the second code cell:
```python
OPENAI_API_KEY = "your-api-key-here"
```

4. **Execute all cells** - full pipeline runs automatically

That's it!

## What's Inside

- 10 diverse fashion products (boho, urban, minimalist, vintage, athletic)
- GPT-4o generates vibe-focused descriptions
- Sentence Transformers for embeddings
- FAISS for vector search
- 5 test queries with performance metrics
- Clean visualizations and reflection

## Usage

```python
# Try any query
try_query("sophisticated professional look for job interview")
try_query("edgy rebellious style with leather")
try_query("comfy cozy weekend vibes")
```

## Performance

- **Latency**: ~30-50ms per query
- **Match Quality**: >70% excellent matches (score >0.7)
- **Error Handling**: Query validation, API retries, graceful fallbacks

## Why This Stack?

**Sentence Transformers over OpenAI embeddings**
- Free and offline (no API costs)
- No network latency
- Privacy (data stays local)
- Quality is comparable for this use case

**FAISS for vectors**
- Blazingly fast
- Scales to millions of vectors
- Battle-tested in production
- Simple API

**GPT-4o for descriptions**
- Captures vibe and emotion better than manual text
- Consistent quality across products

## Future Improvements

**Hybrid search** - Combine semantic + filters (price, category, brand)

**Re-ranking** - Add cross-encoder for fine-grained scoring

**Multi-modal** - CLIP embeddings for image search

**User feedback** - Learn from clicks/purchases

**Query expansion** - Use LLM to expand vague queries

## Scaling Notes

For 10K+ products:
- Batch embeddings in chunks of 500
- Use FAISS IVF index (approximate search)
- Cache embeddings, regenerate only on changes
- Consider Pinecone/Qdrant for 1M+ vectors

## Assignment Requirements

✅ **Data Prep**: 10 products with GPT-4o descriptions
✅ **Embeddings**: 768-dim vectors from sentence transformers
✅ **Vector Search**: FAISS with cosine similarity
✅ **Testing**: 5 diverse queries with metrics
✅ **Reflection**: What worked, edge cases, improvements

### Scoring Criteria

- **Code Quality (30%)**: Clean, simple, well-structured
- **Accuracy/Eval (30%)**: Multiple test cases, clear metrics
- **Innovation (20%)**: GPT-4o integration, robust error handling
- **Process (20%)**: Organized workflow, clear documentation

## Files

```
assignment/
├── vibe_matcher.ipynb    # Main notebook (run this!)
├── README.md             # This file (includes intro)
└── .git/                 # Git repo
```

## Submission

**Deliverables Required:**
1. ✅ Notebook with outputs: `vibe_matcher.ipynb`
2. ✅ 1-paragraph intro: See "Why This Project?" section above

**How to Save Notebook with Outputs:**

After running all cells successfully:

**In Jupyter:**
- File → Save and Checkpoint
- Outputs are automatically saved

**In Google Colab:**
- File → Download → Download .ipynb
- Or: File → Save a copy in Drive

**Verify outputs are saved:**
```bash
# Should show cell outputs
jupyter nbconvert --to html vibe_matcher.ipynb
```

**Submission Links:**
- **GitHub**: https://github.com/AddyB0t/assignment
- **Colab**: Upload `vibe_matcher.ipynb` to Google Drive, then right-click → Open with → Google Colaboratory → Share

**Deadline**: November 11, 2025

---

Built with OpenAI, Sentence Transformers, and FAISS. No fluff, just what works.
