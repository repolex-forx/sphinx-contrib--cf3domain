# Repolex Knowledge Graph of sphinx-contrib/cf3domain

RDF knowledge graph data for [sphinx-contrib/cf3domain](https://github.com/sphinx-contrib/cf3domain), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [rlex](https://github.com/repolex-ai/rlex) query tool:

```bash
cargo install --git https://github.com/repolex-ai/rlex
```

Verify the install:

```bash
rlex --help
```

**rlex is designed to be used primarily by LLMs in a terminal.** Start up your favorite AI assistant and ask it to use rlex. It handles the SPARQL — you just ask questions in plain English.

To load this repo's data:

```bash
rlex download sphinx-contrib/cf3domain
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 6b0797ba829964787cc308debc8ac68ad2bff505
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 6b0797ba829964787cc308debc8ac68ad2bff505
│           └── chunk-001.nq.gz
├── blob
│   ├── 1a5fc92b416de96abfc58e8d61c29ee1664a966d.nq.gz
│   ├── 3c4b0b081053192d408d02dcd992a5d43bc40816.nq.gz
│   ├── 78f35d913f873221174dd38c3aecd28d5a4da965.nq.gz
│   ├── 870f669c96bd749fb237e50ecea80dfc9250e69e.nq.gz
│   ├── b5a7dc29ef0f7f3593b1c61cfc5dfe8a17d3918c.nq.gz
│   ├── c024d81916ae382a2f32ee4b8e686a34638bd2c6.nq.gz
│   └── dcc5796a1747f9e5fc24cf341217c66b1345db60.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 6b0797ba829964787cc308debc8ac68ad2bff505.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 13 files
```

| Directory | What it contains |
|-----------|-----------------|
| `blob/` | Per-file AST graphs, content-addressed by git blob SHA. Each file in the source repo gets its own graph. |
| `aggregate/ast/` | Combined AST graph per parsed commit. Merges all blob graphs for a snapshot of the entire codebase at that point. |
| `aggregate/lsp/` | Language Server Protocol enrichment: resolved symbols, definitions, references, and type information. |
| `aggregate/dataflow/` | Interprocedural data flow edges between functions and modules. |
| `aggregate/repolex/` | Combined graph (AST + LSP + dataflow) per commit. |
| `commit/` | Git commit metadata (author, date, message, parent links). |
| `branch/` | Branch metadata. |
| `tag/` | Tag metadata. |
| `filetree/` | File tree snapshots per commit (which files existed and their blob SHAs). |
| `audit/` | Code architecture and graph audit reports per commit. |

## Source repository

[sphinx-contrib/cf3domain](https://github.com/sphinx-contrib/cf3domain)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
