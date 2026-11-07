# Repolex Knowledge Graph of plotly/all-in-ai-demo-app

RDF knowledge graph data for [plotly/all-in-ai-demo-app](https://github.com/plotly/all-in-ai-demo-app), parsed by [repolex](https://repolex.ai).

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
rlex download plotly/all-in-ai-demo-app
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 95bd667a65e30c56f40f92cf94b7ba88c6d37263
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 95bd667a65e30c56f40f92cf94b7ba88c6d37263
│           └── chunk-001.nq.gz
├── blob
│   ├── 04c726af2307bd136fdd49645648e9e1858f9f4b.nq.gz
│   ├── 0760ad8789d0190758668245dc61f1435470605e.nq.gz
│   ├── 28021db49f2d3d191cc525287eefcdc36de0e1be.nq.gz
│   ├── 31253b4e5268104efe0c8bf80d8fdef7fb56a329.nq.gz
│   ├── 31fe8678127967079bf1204ce4303f552b4ae9d5.nq.gz
│   ├── 35ac70953c93e3ff9ecb54eaec573bc6cf90adf6.nq.gz
│   ├── 3a6053bb8d13c632328843022be7e8b3745f8142.nq.gz
│   ├── 3d8a849ed5c61a8b755660c3978d95a53c437bd0.nq.gz
│   ├── 48eed8cc6195f731dfc735bc313723efedcb428c.nq.gz
│   ├── 5767a7862bb189839f4dde6677a36f70f80363a9.nq.gz
│   ├── 63f9d59c992058b529111aaaa346cee036ff66d5.nq.gz
│   ├── 70677956e16e12b1b95fa7b89fe327950a7dcebc.nq.gz
│   ├── bc8371522911dae5c57fa15028a9c84eeb316709.nq.gz
│   ├── d3cd9a5e83e2352164a713957680a82b85f235a2.nq.gz
│   ├── f9378266cc79bff26da7cb08fcb3b182c4207b90.nq.gz
│   └── f943215243f9754a22ae2c800d06ad40a0b5e783.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 95bd667a65e30c56f40f92cf94b7ba88c6d37263.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 24 files
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

[plotly/all-in-ai-demo-app](https://github.com/plotly/all-in-ai-demo-app)

---
*Parsed on 2026-11-07 by [repolex](https://repolex.ai)*
