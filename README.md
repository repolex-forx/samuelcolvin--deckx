# Repolex Knowledge Graph of samuelcolvin/deckx

RDF knowledge graph data for [samuelcolvin/deckx](https://github.com/samuelcolvin/deckx), parsed by [repolex](https://repolex.ai).

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
rlex download samuelcolvin/deckx
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── ff0a0c464451d9621d40c8b223185a7a7a07f517
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── ff0a0c464451d9621d40c8b223185a7a7a07f517
│           └── chunk-001.nq.gz
├── blob
│   ├── 00d4d6a8cef8f7b99432bbd1c8296816244b987d.nq.gz
│   ├── 019756dc94ad3329b29af57b5cbe485dafab15e0.nq.gz
│   ├── 01bf9000b6c5a77e2d7e768239931f0551e6428d.nq.gz
│   ├── 04efac63a97d3cb0b1b1bc57798fd56e8f898c3b.nq.gz
│   ├── 06575a261119c30d9d954e8daeca838fb7256181.nq.gz
│   ├── 18bc41386b45714ad4fe273aaf21c798a88094a5.nq.gz
│   ├── 195580b0cc7432724c98a12c20433ccb26f6e15b.nq.gz
│   ├── 1c1aa9b1bed3206f05b96fbbce302b330e0b633b.nq.gz
│   ├── 2588eabde331673f694826a53cabd804d6a574d3.nq.gz
│   ├── 2c9d38391e24e51d46493e359cb4534affd13a53.nq.gz
│   ├── 35248b0ac5b926d22fcdaa4176811d7654d65393.nq.gz
│   ├── 3d77c1de8ae35c64b5a8a69c89cf14fd9750e463.nq.gz
│   ├── 4a749a566353ac40a6d8bd50dce2ca4bb7df62f0.nq.gz
│   ├── 55f7cc71b7e45c543aa06a8abccadbf6b687d204.nq.gz
│   ├── 5838b005c8e1ef75f34efa436bc448f3fbf15382.nq.gz
│   ├── 5cb42f821185fb2b12ed6eaa3db6e1162e178960.nq.gz
│   ├── 681311eb9cf453d0faddf3aacaec7357e97ba8e9.nq.gz
│   ├── 6c72184384c888a4723fa269106ff020e3458fa3.nq.gz
│   ├── 6de6142dd978f94eee3ae1e07cbbd83dc887428d.nq.gz
│   ├── 8a170f004649c5244e896854b8c17348cf12e49b.nq.gz
│   ├── 9161db886f05df62b80193844e71ce3e20b45ac1.nq.gz
│   ├── 9314a0a8793046ee06fa77a96bc80bec911c014e.nq.gz
│   ├── 93efe659187dca48db6a1a8241164899c733a80c.nq.gz
│   ├── 99adcd08898932a399e2e27b7b780a2214970a8d.nq.gz
│   ├── be3a8c76af8d58763fdb77425b3f7a995f06858b.nq.gz
│   ├── c6d0c180b34a474b0c9b7592380944e33f48a09f.nq.gz
│   ├── c87754aad218ff2a1fbddbe941c65786d6bee5a7.nq.gz
│   ├── c8ce7013786e57afaa52f9d495ea3b0bfda1869e.nq.gz
│   ├── cbbb65f4846f13a1054e3040a5f6c9671a16a0ac.nq.gz
│   ├── d12e9612c9763c6a899b53fea3d180dbafe5a25c.nq.gz
│   ├── de9730c5e9747be215921cae70ef7d5c7b0cc147.nq.gz
│   ├── ec5a439ccecb7abeea1ef1ac039b3dd398dd916b.nq.gz
│   ├── fe4f4f6a8a15946b45a9b6f06a4e90a5b786e949.nq.gz
│   └── ff3fb13bfbee0ca0b34c2fe21bfcb566183f25f6.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── ff0a0c464451d9621d40c8b223185a7a7a07f517.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 41 files
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

[samuelcolvin/deckx](https://github.com/samuelcolvin/deckx)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
