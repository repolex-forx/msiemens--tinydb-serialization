# Repolex Knowledge Graph of msiemens/tinydb-serialization

RDF knowledge graph data for [msiemens/tinydb-serialization](https://github.com/msiemens/tinydb-serialization), parsed by [repolex](https://repolex.ai).

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
rlex download msiemens/tinydb-serialization
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 685b8192995e9761af725dac247887feaeeca74f
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 685b8192995e9761af725dac247887feaeeca74f
│           └── chunk-001.nq.gz
├── blob
│   ├── 1f6ae139aa4201f6455ab34a5c904c41686373f7.nq.gz
│   ├── 20d3b2eec71f8849da848f9c353c315777f5fe5e.nq.gz
│   ├── 374be89292f83edddbfb073583a052037ea151b6.nq.gz
│   ├── 5093635580f40160a1660d1221a2e979054b9b50.nq.gz
│   ├── 68ea411bc5a86822e7449ed13f6353834267411d.nq.gz
│   ├── 721ff95eaeed84b25975ac2c6ad48a5a940ed297.nq.gz
│   ├── 86774dfaf3664a7424afe57d3aff94ffdff12910.nq.gz
│   ├── c3dbf616619f47c48422f6d512983fc9a09521cf.nq.gz
│   ├── d9005f2cc7fc4e65f14ed5518276007c08cf2fd0.nq.gz
│   ├── f146f1e90fe9ae66f5ebda64401b50119c0e60e6.nq.gz
│   └── fc3635e95386e18df05de80a5c54f61cd2305b83.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 685b8192995e9761af725dac247887feaeeca74f.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 19 files
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

[msiemens/tinydb-serialization](https://github.com/msiemens/tinydb-serialization)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
