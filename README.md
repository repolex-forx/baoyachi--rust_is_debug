# Repolex Knowledge Graph of baoyachi/rust_is_debug

RDF knowledge graph data for [baoyachi/rust_is_debug](https://github.com/baoyachi/rust_is_debug), parsed by [repolex](https://repolex.ai).

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
rlex download baoyachi/rust_is_debug
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 6f64716442030267ff23ae446b1dd791880c8fec
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 6f64716442030267ff23ae446b1dd791880c8fec.nq.gz
│   └── repolex
│       └── 6f64716442030267ff23ae446b1dd791880c8fec
│           └── chunk-001.nq.gz
├── blob
│   ├── 194b5a15753a355ea8a129fd98da21b7f90d5792.nq.gz
│   ├── 2e049011e7eceb5d8b29a0f70f116e8b1a588c29.nq.gz
│   ├── 3d72afe060c7972da3e0f440e546c216974d8a19.nq.gz
│   ├── 3ed56e9f4f34e455c3ae08d66a1df1ede0a9ce24.nq.gz
│   ├── 5f081280d9af5813b96e26dc151158a55faf61c8.nq.gz
│   ├── 84830f366e1d2e34b32f72c76bb72d56d5288754.nq.gz
│   ├── 85b6993e83a588bfc93fde295b30a353986534a2.nq.gz
│   ├── 8ea4b20b0d2c37b72ad1ea0fd119df3b7b21214c.nq.gz
│   ├── 9a67f6435fa78ec982fa9dba15a768315e49f697.nq.gz
│   ├── b83f1ba5d344df33e8e181e499b4ff04e33c31e7.nq.gz
│   └── d27c28eb292cf62157e639121297bfc76d4d86fc.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 6f64716442030267ff23ae446b1dd791880c8fec.nq.gz
├── filetree
│   └── 6f64716442030267ff23ae446b1dd791880c8fec.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 21 files
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

[baoyachi/rust_is_debug](https://github.com/baoyachi/rust_is_debug)

---
*Parsed on 2026-11-21 by [repolex](https://repolex.ai)*
