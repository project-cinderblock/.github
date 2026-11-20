# Project Cinderblock 🧱

**Locally hosted Ruby on Rails computational laboratories for modeling complex, evolving data, paired with Model Context Protocol (MCP) servers for AI-agent exploration.**

[Project Cinderblock](https://github.com/project-cinderblock) is an open-source collection of 12 MIT-licensed repositories (6 Rails 8.1+ research platforms and 6 companion TypeScript MCP servers). Each laboratory applies relational domain modeling, `pgvector` semantic manifolds, and local LLM pipelines to a distinct scientific or humanities discipline.

## Why Local Rails Instead of Notebooks

Most data and AI projects start in a Jupyter Notebook by default. Notebooks work well for static, rectangular CSVs and linear, procedural calculations. They break down the moment your data becomes an evolving, graph-shaped knowledge domain:

* **Flat inputs vs. real relationships:** Dataframes expect uniform rows and columns. When entities connect in dense many-to-many webs, forcing them into flat tables scatters brittle join logic across cells.
* **Linear execution vs. living state:** Notebooks run top to bottom, yet practitioners jump between cells and mutate variables out of order, creating hidden state that fails on a fresh kernel.
* **Static schemas vs. ongoing discovery:** Notebooks assume someone already cleaned and froze the dataset. They are poor containers for knowledge that grows, shifts, and gets corrected every week.

Notebooks are great scratchpads. They are terrible databases.

As outlined in [Modeling Complex Data](https://blog.macron1.io/articles/modeling-complex-data), Project Cinderblock treats the schema as the model:

* **Relational Domain Modeling:** Built on Ruby on Rails and PostgreSQL, every core concept is a first-class Active Record model with explicit join models for graph edges, versioned migrations for schema evolution, and boundary validations that keep bad data out.
* **Single-Store Hybrid Retrieval:** Semantic embeddings (1024-dimensional HNSW indexes via `pgvector`) live in PostgreSQL right beside relational tables and foreign keys. You get semantic entry points, relational graph traversal, and SQL-filtered similarity search in one database, without a separate vector store or fragile sync pipeline.
* **4-Layer LLM Extraction Pipeline:** Unstructured source material moves through four distinct layers: **Ingestion** (immutable raw source records), **Extraction** (strict target-schema prompting), **Validation** (Active Record constraints and deduplication), and **Provenance** (source record, excerpt, model version, and timestamp).
* **A Pragmatic Two-Stage Workflow:** Keep the living knowledge graph in Rails as the operational source of truth. When you need statistical verification, clustering diagnostics, or visual plots, export a clean slice to Jupyter, then feed structural discoveries back into your Rails models.

## Shared Architecture

Every laboratory in Project Cinderblock runs locally without cloud lock-in and shares a consistent, production-tested stack:

* **Application & Modeling:** Ruby 3.4+, Rails 8.1+, PostgreSQL 16+, `pgvector` (1024-dim HNSW)
* **Local AI & Background Jobs:** Ollama, RubyLLM, Sidekiq
* **Interface:** Hotwire, Tailwind CSS
* **Agent Connectivity:** Companion TypeScript MCP servers communicating over stdio JSON-RPC (compatible with Claude Desktop, Cursor, Antigravity, and custom agent harnesses)

## The Computational Laboratories

Each domain pairs a Rails computational laboratory with a dedicated TypeScript MCP server so researchers and AI agents can search, cluster, traverse, and synthesize across the same underlying knowledge graph.

* **Chemist** ([`chemist`](https://github.com/project-cinderblock/chemist) | [`chemist-mcp`](https://github.com/project-cinderblock/chemist-mcp)): Built for organic chemists, medicinal chemists, materials scientists, and computational biochemists. Maps and clusters chemical classes, molecules, functional group manifolds, reactivity profiles, and bioisosteric motifs. Companion MCP server exposes 51 tools across 8 modules, 4 resources, and 2 prompt templates.
* **Physicist** ([`physicist`](https://github.com/project-cinderblock/physicist) | [`physicist-mcp`](https://github.com/project-cinderblock/physicist-mcp)): Built for theoretical physicists, high-energy phenomenologists, quantum information scientists, and condensed matter researchers. Models particle groups, subatomic particles, quantum state manifolds, gauge invariants, and spin-statistics. Companion MCP server exposes 51 tools across 8 modules, 4 resources, and 2 prompt templates.
* **Biologist** ([`biologist`](https://github.com/project-cinderblock/biologist) | [`biologist-mcp`](https://github.com/project-cinderblock/biologist-mcp)): Built for evolutionary biologists, ecologists, ethologists, and organismal taxonomists. Maps biomes, species and populations, individual organisms, convergent adaptations, trophic strategies, and phenotypic manifolds. Companion MCP server exposes 51 tools across 8 modules, 4 resources, and 3 prompt templates.
* **Astronomer** ([`astronomer`](https://github.com/project-cinderblock/astronomer) | [`astronomer-mcp`](https://github.com/project-cinderblock/astronomer-mcp)): Built for astrophysicists, planetary scientists, extragalactic astronomers, and stellar cartographers. Synthesizes cosmic structures, star systems, celestial bodies, orbital dynamics, and planetary manifolds. Companion MCP server exposes 51 tools across 8 modules, 4 resources, and 2 prompt templates.
* **Statesman** ([`statesman`](https://github.com/project-cinderblock/statesman) | [`statesman-mcp`](https://github.com/project-cinderblock/statesman-mcp)): Built for political scientists, international relations scholars, geostrategists, and urban economists. Models world states, metropolitan centers, institutional trajectories, strategic geography, and urban power networks. Companion MCP server exposes 51 tools, 4 resources, and 2 geopolitical analysis prompts.
* **Syncretica** ([`syncretica`](https://github.com/project-cinderblock/syncretica) | [`syncretica-mcp`](https://github.com/project-cinderblock/syncretica-mcp)): Built for theologians, comparative religionists, archaeologists, and mythologists. Maps deities, pantheons, structural mythemes, and cross-cultural religious parallels to surface non-obvious connections across traditions. Companion MCP server exposes 28 tools, 4 resources, and 2 analysis prompts.

## Further Reading & License

* **Architecture Essay:** [Modeling Complex Data](https://blog.macron1.io/articles/modeling-complex-data) by Leonid Medovyy
* **Organization:** [github.com/project-cinderblock](https://github.com/project-cinderblock)
* **License:** All repositories in Project Cinderblock are released under the MIT License.
