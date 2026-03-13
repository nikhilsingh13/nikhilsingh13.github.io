---
layout: single
title: "Building a Graph RAG Pipeline."
date: 2026-03-13
author: "Nikhil Singh"
excerpt: "Building a lightweight agentic workflow using GraphRAG, knowledge graphs & semantic caching."
header:
  overlay_image: "./img/bg4-rag-gnn.png"
use_math: true
author_profile: true
toc: true
toc_label: "Contents"
toc_icon: "list"
classes: wide
---

## Introduction

### Graph RAG?

**Graph RAG** takes traditional vector search one step ahead by treating the provided knowledge base as a **network of connected entities** instead of isolated text chunks.

**Traditional RAG:**
```
Query → Vector Search → Top K chunks → LLM → Answer
```

### Workflow
```
Query →  Semantic Cache →  (hit)    →  return cached response
                           (miss)   → Vector Search → Initial nodes
                                    → Traverse relationships
                                    → Graph traversal
                                    → Rerank combined context
                                    → LLM → Answer
```

### Building Blocks
#### Step 1: PDF Extraction

Cleaning text from academic PDFs, there are a lot of python libraries which can help or automate the process. These libraries struggle with figures, numbers, derivations and coordinates in the text. 
In the current post and demo, I've mitigated the issue related to figures by simply acknowledging it in system prompt provided to the QnA LLM.
  
#### Step-2: Entity extraction


## Tech Stack
- Python 3.14
- PyMuPDF
- sentence-transformers
- DuckDB (VSS)
- NetworkX
- HuggingFace Inference API
- Gradio
- uv

---
## Additional Resources

**Learn More:**
- [LlamaIndex PropertyGraph Guide](https://docs.llamaindex.ai/en/stable/examples/property_graph/property_graph_custom_retriever/)
- [Microsoft GraphRAG Paper](https://arxiv.org/abs/2404.16130)
- [Jerry Liu's Thread on Graph RAG](https://twitter.com/jerryjliu0/status/1797057726994092492)

**Tools to Explore:**
- Neo4j - If you need full graph DB.
- Microsoft GraphRAG - For enterprise synthesis needs.
- Pinecone + metadata filtering - Simple alternative to graphs.

**Questions or want to discuss your specific use case?** Connect with me on <a href="https://www.linkedin.com/in/singh-nikhil" target="_blank">LinkedIn</a> or <a href="https://twitter.com/nikhilsingh_1" target="_blank">Twitter</a>.

---