# Repolex Knowledge Graph of aio-libs/prepare-coverage

RDF knowledge graph data for [aio-libs/prepare-coverage](https://github.com/aio-libs/prepare-coverage), parsed by [repolex](https://repolex.ai).

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
rlex download aio-libs/prepare-coverage
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 4a1ef3620e2cfa54e7fe18f71488df7904f0578d
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 4a1ef3620e2cfa54e7fe18f71488df7904f0578d
│           └── chunk-001.nq.gz
├── blob
│   ├── 125ffc0dbddf1d48ca406d03624ce69bcb87ecbe.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 45fa05c268577aa14858f034717b0737df3b1d26.nq.gz
│   ├── 8cbf2519d5a312c64f78a77cf4112271396f3016.nq.gz
│   ├── 9863b8414ed03d602d6bf0b448c2cbf2978ff815.nq.gz
│   ├── a4ba56349dc9330702121015b20d8d724ff4c731.nq.gz
│   ├── a99709f7170210ea9a1153178fd042ed0c374482.nq.gz
│   ├── ae8dd8e88a6d4126e24f3dbf20aefa95413f9f73.nq.gz
│   ├── b6e47617de110dea7ca47e087ff1347cc2646eda.nq.gz
│   └── ca26e3b7c30538a15e19c88d6ba84f0d144c3a0f.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 4a1ef3620e2cfa54e7fe18f71488df7904f0578d.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 17 files
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

[aio-libs/prepare-coverage](https://github.com/aio-libs/prepare-coverage)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
