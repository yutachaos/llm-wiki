# LLM Wiki (karpathy gist)

- 取得元: https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f
- 取得日: 2026-07-02

---

# LLM Wiki: Personal Knowledge Base Pattern

## Core Concept

The LLM Wiki pattern proposes building a persistent, maintained knowledge base rather than relying on retrieval-augmented generation (RAG) that rediscovers information on every query. As the document explains, "the wiki is a persistent, compounding artifact" where cross-references and syntheses accumulate over time.

## Three-Layer Architecture

The system comprises:

1. **Raw sources** — immutable input documents the LLM reads but never modifies
2. **The wiki** — LLM-generated markdown pages that the system actively maintains
3. **The schema** — configuration document governing wiki structure and workflows

## Key Operations

**Ingestion** involves the LLM reading new sources, extracting key information, and integrating findings across 10-15 existing wiki pages simultaneously.

**Querying** treats the wiki as the primary knowledge store, with the LLM synthesizing answers from existing pages rather than re-deriving insights from raw sources.

**Linting** involves periodic health checks for contradictions, stale information, orphaned pages, and missing cross-references.

## Navigation Tools

Two special files support navigation:
- **index.md** — content-oriented catalog organized by category
- **log.md** — append-only chronological record of wiki evolution

## Why This Approach Works

The document notes that "the tedious part of maintaining a knowledge base is not the reading or the thinking — it's the bookkeeping." LLMs eliminate this maintenance burden, allowing knowledge bases to compound rather than stagnate.
