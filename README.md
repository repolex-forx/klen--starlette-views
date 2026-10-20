# Repolex Knowledge Graph of klen/starlette-views

RDF knowledge graph data for [klen/starlette-views](https://github.com/klen/starlette-views), parsed by [repolex](https://repolex.ai).

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
rlex download klen/starlette-views
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── d1447bdf08c88749eded2a2125a3023991c217b4
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── d1447bdf08c88749eded2a2125a3023991c217b4
│           └── chunk-001.nq.gz
├── blob
│   ├── 178e66ffe768300cd50ddddd190ecc5e14c4e241.nq.gz
│   ├── 17b21a42ef57718542e9e12b45ce507584a9dafa.nq.gz
│   ├── 20c850c6a393ec7d20a769f5602ead5f785d716d.nq.gz
│   ├── 2247d5f95a7193c7221b9464debe167763b4fae3.nq.gz
│   ├── 349fa04ce5d3d61d60fc670a83062858d2e79266.nq.gz
│   ├── 3612cf5ca29646155365e898a05b701b1a1ca4ab.nq.gz
│   ├── 7f8472997c0f75f0b89fa82e94883b0110049402.nq.gz
│   ├── 80611a29c8c2c1072105f2245fc26151fe747a64.nq.gz
│   ├── d24856cce4dd0283a36f01d6f2ad710dee8194b7.nq.gz
│   └── d937a870d97cd05918d2ab949a13e0e3d83b2c90.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── d1447bdf08c88749eded2a2125a3023991c217b4.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 16 files
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

[klen/starlette-views](https://github.com/klen/starlette-views)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
