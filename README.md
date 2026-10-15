# Repolex Knowledge Graph of pylint-dev/pylint-celery

RDF knowledge graph data for [pylint-dev/pylint-celery](https://github.com/pylint-dev/pylint-celery), parsed by [repolex](https://repolex.ai).

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
rlex download pylint-dev/pylint-celery
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 4edf639f291b677270e792f5c045c3cc2ac3a664
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 4edf639f291b677270e792f5c045c3cc2ac3a664
│           └── chunk-001.nq.gz
├── blob
│   ├── 3c8b70850c6bc5c45cbabf2a8d512330d37d8e77.nq.gz
│   ├── 3ef4282d095e355d66dc4d77e9ad3a9f76e695dd.nq.gz
│   ├── 71dd854c62a98cd9896b73147a00184348e5e334.nq.gz
│   ├── 98139d32f2abd61f0b5b5ab43fde57524be32653.nq.gz
│   ├── b0853f52b1b054eb2db39cf00459eebf09b750c3.nq.gz
│   ├── c0c97e91278b759f28f1cb10079bcf2e3879c363.nq.gz
│   ├── d2d6f360b5d1ea91375f06547df0048ec47a4862.nq.gz
│   ├── db9329899779e3e951f328ed116fe78cd3398acf.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── f5e1d38e8360a7e8fa5dbf4a2c630e9d8f93528c.nq.gz
│   └── f6ccadffd93d35e2d2cb67d793d2111c37a838a7.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 4edf639f291b677270e792f5c045c3cc2ac3a664.nq.gz
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

[pylint-dev/pylint-celery](https://github.com/pylint-dev/pylint-celery)

---
*Parsed on 2026-10-15 by [repolex](https://repolex.ai)*
