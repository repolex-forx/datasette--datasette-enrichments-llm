# Repolex Knowledge Graph of datasette/datasette-enrichments-llm

RDF knowledge graph data for [datasette/datasette-enrichments-llm](https://github.com/datasette/datasette-enrichments-llm), parsed by [repolex](https://repolex.ai).

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
rlex download datasette/datasette-enrichments-llm
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 40e7923095605f8a39d202031f86a4d76423d92f
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 40e7923095605f8a39d202031f86a4d76423d92f
│           └── chunk-001.nq.gz
├── blob
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 4aec663548c3c074609852b837b9a55115bba525.nq.gz
│   ├── 5e718cef78a5726d2850559da40def0581775eac.nq.gz
│   ├── 63ff949fbb2595055ff1b813527ee50744768058.nq.gz
│   ├── 7a17a8a8f21b23f799bf668c0c86619f7298161c.nq.gz
│   ├── b2dfc078d5f20915d4c8b3a8eb2c99776d32de15.nq.gz
│   ├── d0d5ce3ee8fa6494d61b4f902ee7d8de943e1b36.nq.gz
│   └── e0a03bc5772904d45b119f9edc09e6530b209b08.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 40e7923095605f8a39d202031f86a4d76423d92f.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 16 files
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

[datasette/datasette-enrichments-llm](https://github.com/datasette/datasette-enrichments-llm)

---
*Parsed on 2026-10-12 by [repolex](https://repolex.ai)*
