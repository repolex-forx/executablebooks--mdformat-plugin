# Repolex Knowledge Graph of executablebooks/mdformat-plugin

RDF knowledge graph data for [executablebooks/mdformat-plugin](https://github.com/executablebooks/mdformat-plugin), parsed by [repolex](https://repolex.ai).

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
rlex download executablebooks/mdformat-plugin
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 38530fd7fa9eeac302cb89314ab043147db7e51a
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 38530fd7fa9eeac302cb89314ab043147db7e51a
│           └── chunk-001.nq.gz
├── blob
│   ├── 1c98271eee002ca16ff436617bf5731f0ab656ef.nq.gz
│   ├── 2a08e1cec4aa469911e5692d0c23f0635b63ad41.nq.gz
│   ├── 2dbe033b6c9076223ceb94eb6cded6e79d655305.nq.gz
│   ├── 31d6be20fe946cd21328f682f823ab79c7194ce5.nq.gz
│   ├── 41054b978f397e482f675673fffcecb06b6dbf34.nq.gz
│   ├── 68fc3bf1185e19a3cff47a7dca50a5f312a38925.nq.gz
│   ├── 6e4b36f69920d70a52e297f13aa5ea374d7958b1.nq.gz
│   ├── 8fff61c793824acdd7c77c5546cc23f5604e8468.nq.gz
│   ├── 9706ae02d55cd3c25c5804d08e14819abb2da7fc.nq.gz
│   ├── c284ba3d982fd2aee9983bee1a3ec1794970ebb2.nq.gz
│   ├── d728245d7ba91638e2f291dc5a0900434bae8d98.nq.gz
│   ├── e06ffb1f404dd0b81395d397042a7d95f96c76dd.nq.gz
│   └── e4817750c01d0c507074cdf8b7948f20b447be72.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 38530fd7fa9eeac302cb89314ab043147db7e51a.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 21 files
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

[executablebooks/mdformat-plugin](https://github.com/executablebooks/mdformat-plugin)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
