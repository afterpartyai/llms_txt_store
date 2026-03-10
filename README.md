
# SN33 LLMs.txt Dataset
### AI-Structured Web Intelligence from Common Crawl

## Overview

This repository publishes **machine-readable `llms.txt` files generated from large‑scale SN33 processing of Common Crawl data**.

SN33 analyzes web content at scale using named-entity recognition, semantic tagging, and structural extraction to create **AI-ready knowledge surfaces for websites**. These surfaces make it dramatically easier for LLM agents, MCP servers, and AI applications to understand the structure and meaning of a site without needing to crawl and interpret raw HTML.

Instead of forcing every AI system to rediscover the same information, this dataset provides **structured semantic summaries of the web**.

The goal is simple:

> **Make the web easier for AI systems to understand, navigate, and use.**

This initial release contains **~1000 processed sites** as a test dataset. The pipeline is designed to scale to millions of domains.

---

# Why This Exists

Large language models interact with the web very differently than humans.

Human browsing relies on:
- visual structure
- layout
- navigation menus
- contextual reading

AI systems rely on:
- semantic signals
- entity relationships
- structured representations
- machine-readable summaries

Raw HTML is extremely inefficient for AI systems to interpret. Every model must repeatedly:

1. crawl pages
2. extract structure
3. infer entities
4. build semantic context

This repository eliminates that redundancy.

Each `llms.txt` file provides a **compressed semantic representation of a site**, generated once and reusable by any AI system.

---

# Benefits

## For AI Developers

- Faster agent reasoning about websites
- Reduced token usage when interacting with web content
- Cleaner integration with MCP servers and agent frameworks
- Deterministic lookup of structured site metadata

## For LLM Applications

- Structured entity and topic understanding
- Improved navigation of large documentation sites
- Reduced hallucination when referencing external sources
- More reliable grounding of responses

## For the Open Web

- Shared AI infrastructure layer
- Reduced redundant crawling and parsing
- Public, open dataset usable by anyone
- Foundation for large-scale AI-native web indexing

## For the Bittensor Ecosystem

- Demonstrates **real-world utility of SN33**
- Converts raw crawl data into usable AI infrastructure
- Provides reusable semantic datasets for model training and evaluation
- Establishes SN33 as a **data intelligence layer for decentralized AI**

---

# What SN33 Does

SN33 processes large volumes of Common Crawl data and transforms raw HTML into structured AI resources.

Core steps include:

1. **Content extraction**
   - Parse HTML
   - Normalize text
   - Remove boilerplate

2. **Named Entity Recognition**
   - Identify people
   - organizations
   - technologies
   - locations
   - products
   - concepts

3. **Semantic tagging**
   - classify topics
   - detect relationships
   - identify key themes

4. **Site-level aggregation**
   - combine signals across pages
   - construct domain-level summaries

5. **LLM resource generation**
   - produce standardized `llms.txt` files
   - optimized for agent consumption

The result is a **machine-readable semantic index of a website**.

---

# Repository Structure

This repository organizes `llms.txt` files deterministically based on domain names.

Directory structure:

```
/{tld}/{subdomain_if_any}/{char-exploded-domain}/llms.txt
```

### Examples

| Domain | Repo Path |
|------|------|
| abc.com | com/a/b/c/llms.txt |
| docs.abc.com | com/docs/a/b/c/llms.txt |
| bbc.co.uk | co.uk/b/b/c/llms.txt |
| docs.abc.co.uk | co.uk/docs/a/b/c/llms.txt |
| abc.io | io/a/b/c/llms.txt |
| strongfirst.com | com/s/t/r/o/n/g/f/i/r/s/t/llms.txt |
| abc.com.au | com.au/a/b/c/llms.txt |

---

# Why This Directory Scheme Works

### O(1) Lookup

Given a domain name, the path is deterministic. No global index file is required.

### No Directory Bloat

Each character layer contains at most ~40 entries (a–z, 0–9, hyphen).

This keeps directories well below GitHub limits.

### Browsable

Top-level folders represent TLDs such as:

```
com/
org/
io/
co.uk/
com.au/
```

### Git Friendly

Even with millions of sites, the repository remains manageable because files are small (~5–10 KB each).

### Subdomain Safe

Subdomains map cleanly without collisions:

```
docs.abc.com
abc.com
api.abc.com
```

All resolve to different paths.

---

# Handling Compound TLDs

Many countries use **compound TLD structures** where the registrable domain is not the second-level label.

Examples:

- `bbc.co.uk`
- `abc.com.au`
- `company.co.jp`

To correctly handle these cases, the SN33 crawler includes a list of **143 compound TLDs** derived from the Mozilla Public Suffix List.

Examples include:

| Country | Examples |
|-------|-------|
| UK | co.uk, org.uk, net.uk |
| Australia | com.au, net.au |
| Japan | co.jp, or.jp |
| India | co.in, net.in |
| Brazil | com.br, net.br |
| China | com.cn, org.cn |

This ensures domain paths are generated correctly for global sites.

Source: https://publicsuffix.org/

---

# Example Lookup

To find the semantic summary for:

```
docs.abc.com
```

Navigate to:

```
com/docs/a/b/c/llms.txt
```

To find:

```
strongfirst.com
```

Navigate to:

```
com/s/t/r/o/n/g/f/i/r/s/t/llms.txt
```

---

# Use Cases

### MCP Servers

Agents can fetch a site's `llms.txt` before crawling to gain immediate semantic context.

### LLM Browsers

AI browsers can bootstrap understanding of unfamiliar domains.

### Training Data

Structured entity datasets extracted from web domains.

### Retrieval Systems

Semantic grounding for RAG pipelines.

### AI Search

Improved ranking signals based on domain-level semantics.

---

# Roadmap

This repository begins with a **~200 domain pilot dataset**.

Future stages:

1. **10K domains**
2. **100K domains**
3. **1M domains**
4. **continuous updates from Common Crawl releases**

The long-term goal is to provide **an open semantic layer for the web optimized for AI systems**.

---

# About SN33

SN33 is a subnet in the **Bittensor decentralized AI network** focused on:

- large-scale data processing
- semantic extraction
- AI-ready datasets
- knowledge infrastructure for machine intelligence

SN33 converts massive raw datasets into **structured resources usable by models, agents, and AI applications**.

---

# Contributing

Contributions, improvements, and feedback are welcome.

Future contributions may include:

- additional domain coverage
- improved entity extraction
- better semantic summaries
- additional AI resource formats

---

# License

This dataset is intended to support open AI infrastructure.

See repository license for details.
