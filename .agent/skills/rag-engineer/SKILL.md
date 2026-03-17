---
name: rag-engineer
description: Build production RAG (Retrieval-Augmented Generation) systems. Vector search, embeddings, chunking strategies, re-ranking, and evaluation. Use when building AI features that need external knowledge.
---

# RAG Engineer

> Build AI systems that know what they don't know — and find the right answers.

---

## 1. RAG Architecture

### Core Pipeline

```
Query → Embed → Search → Retrieve → Rerank → Augment → Generate → Evaluate
```

### Component Decisions

| Component | Options | Decision Factor |
|-----------|---------|----------------|
| **Embedding** | OpenAI, Cohere, local | Cost, latency, quality |
| **Vector DB** | Pinecone, Weaviate, Chroma, pgvector | Scale, features, cost |
| **Chunking** | Fixed, semantic, document-aware | Content type, quality needs |
| **Retrieval** | Dense, sparse, hybrid | Accuracy vs speed |
| **Reranking** | Cross-encoder, Cohere, ColBERT | Quality vs latency budget |

---

## 2. Chunking Strategies

### Strategy Selection

| Strategy | Best For | Chunk Size |
|----------|----------|-----------|
| **Fixed-size** | Uniform content | 256-512 tokens |
| **Sentence-based** | Articles, docs | Natural boundaries |
| **Semantic** | Mixed content | Meaning boundaries |
| **Document-aware** | Structured docs | Headers, sections |
| **Recursive** | Code, markdown | Language-specific splits |

### Chunking Principles

| Principle | Application |
|-----------|-------------|
| **Overlap** | 10-20% overlap between chunks |
| **Context preservation** | Don't split mid-sentence/thought |
| **Metadata enrichment** | Attach source, section, position |
| **Size balance** | Not too small (no context), not too large (noise) |

---

## 3. Embedding Best Practices

### Model Selection

| Factor | Consideration |
|--------|--------------|
| **Dimension** | Higher = more nuance, more cost |
| **Task** | Symmetric (search) vs asymmetric (Q&A) |
| **Language** | Multilingual vs single language |
| **Updates** | Fine-tunable vs frozen |

### Optimization

- Normalize vectors for cosine similarity
- Batch embedding requests for throughput
- Cache frequently accessed embeddings
- Consider dimensionality reduction for scale

---

## 4. Retrieval Patterns

### Hybrid Search

```
Retrieval Strategy Decision:
├── Simple keyword match → BM25 (sparse)
├── Semantic understanding → Dense vectors
├── Best of both → Hybrid (BM25 + dense)
└── High precision needed → Hybrid + reranking
```

### Advanced Retrieval

| Pattern | Use Case |
|---------|----------|
| **Multi-query** | Rephrase query 3-5 ways, merge results |
| **HyDE** | Generate hypothetical answer, search with it |
| **Parent-child** | Retrieve small chunk, return parent context |
| **Metadata filter** | Pre-filter by date, source, type |
| **MMR** | Maximize diversity in results |

---

## 5. Context Window Management

### Token Budget

| Component | Allocation |
|-----------|-----------|
| System prompt | 10-15% |
| Retrieved context | 50-60% |
| User query | 5-10% |
| Generation space | 20-30% |

### When Context Overflows

1. Increase top-k and rerank to top-n
2. Compress/summarize retrieved chunks
3. Use map-reduce over chunks
4. Implement iterative refinement

---

## 6. Evaluation Framework

### RAG Metrics

| Metric | What It Measures |
|--------|-----------------|
| **Faithfulness** | Is answer grounded in context? |
| **Relevance** | Are retrieved docs relevant? |
| **Answer quality** | Is the final answer correct? |
| **Completeness** | Does answer cover the question? |
| **Latency** | End-to-end response time |

### Evaluation Tools

| Tool | Purpose |
|------|---------|
| RAGAS | Automated RAG evaluation |
| LangSmith | Tracing and debugging |
| DeepEval | LLM-powered eval |

---

## 7. Production Considerations

### Scaling

| Concern | Solution |
|---------|---------|
| Indexing speed | Batch updates, async processing |
| Query latency | Caching, approximate search (ANN) |
| Storage cost | Compression, tiered storage |
| Freshness | Incremental updates, TTL |

### Anti-Patterns

| ❌ Don't | ✅ Do |
|----------|-------|
| Stuff all context into one prompt | Retrieve and rank selectively |
| Ignore chunk quality | Clean, preprocess, validate data |
| Skip evaluation | Measure faithfulness and relevance |
| One-size-fits-all chunks | Tune chunk size per content type |
| Trust retrieval blindly | Implement confidence thresholds |

---

> **Remember:** RAG quality = Data quality × Retrieval quality × Generation quality. Most failures start with bad data or bad chunking.
