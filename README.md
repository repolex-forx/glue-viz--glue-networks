# Repolex Knowledge Graph of glue-viz/glue-networks

RDF knowledge graph data for [glue-viz/glue-networks](https://github.com/glue-viz/glue-networks), parsed by [repolex](https://repolex.ai).

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
rlex download glue-viz/glue-networks
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── a59cb1858e9a4bab65e749d8573f69adc5c69bd8
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── a59cb1858e9a4bab65e749d8573f69adc5c69bd8
│           └── chunk-001.nq.gz
├── blob
│   ├── 131d913ccb478874f8536cf0ee9bed419a387d15.nq.gz
│   ├── 15ae24368f87ffdb153fe5a356b4bc199d48dd86.nq.gz
│   ├── 2c49e15f5f3d941dfeda7f8b8b1b4dda7f8e93ae.nq.gz
│   ├── 2c7fb76a5b11645bac5f0883ca452e5bf80af114.nq.gz
│   ├── 47b46142912370a8dcbbd5337fdd1b52e81c8614.nq.gz
│   ├── 76fe15da520fb89b10ff5edfa8e58614a99c80dd.nq.gz
│   ├── b29d8f6fc437020e9e2fc3ba534b96739cf20b50.nq.gz
│   ├── c15a99bfd33ee767051226a2d27bb7426b0b50de.nq.gz
│   ├── d2c4023263212dda7cfc6d42a74f7aa55e701513.nq.gz
│   ├── dd03c42f04d9f702cbb5195bbd872a699f2e1d6a.nq.gz
│   ├── de3cd94d005cb6c4b5f533ae5bba970bbff5082b.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e812ca93872683d872b78e0736220552a4d9ed49.nq.gz
│   └── fe09f78a8e09f60a7c21178b856f935f4f3b272f.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── a59cb1858e9a4bab65e749d8573f69adc5c69bd8.nq.gz
├── issue
│   └── issue.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 21 files
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

[glue-viz/glue-networks](https://github.com/glue-viz/glue-networks)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
