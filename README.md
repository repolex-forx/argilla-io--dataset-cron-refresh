# Repolex Knowledge Graph of argilla-io/dataset-cron-refresh

RDF knowledge graph data for [argilla-io/dataset-cron-refresh](https://github.com/argilla-io/dataset-cron-refresh), parsed by [repolex](https://repolex.ai).

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
rlex download argilla-io/dataset-cron-refresh
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── b8b61ad2d4aa880905bdbfab57822e71d95bba19
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── b8b61ad2d4aa880905bdbfab57822e71d95bba19
│           └── chunk-001.nq.gz
├── blob
│   ├── 52d9fb4e61151cb7c458cfdbd7eddbc2c3fbb026.nq.gz
│   ├── 5944010fefdf4676434882e37cdfb800c9e99c75.nq.gz
│   ├── 9422e98b69590530f60eac2dae629cf4e772d9bf.nq.gz
│   ├── bd0c97a9cbac57e947494a8fdde06863958d2f54.nq.gz
│   ├── c2eabecac229425be9003d3f259451381494ff1c.nq.gz
│   └── f80508aa8c82787b3d82e3d5436d1e0ad9842fe9.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── b8b61ad2d4aa880905bdbfab57822e71d95bba19.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 14 files
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

[argilla-io/dataset-cron-refresh](https://github.com/argilla-io/dataset-cron-refresh)

---
*Parsed on 2026-11-08 by [repolex](https://repolex.ai)*
