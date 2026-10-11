# Repolex Knowledge Graph of bottlepy/bottle-inject

RDF knowledge graph data for [bottlepy/bottle-inject](https://github.com/bottlepy/bottle-inject), parsed by [repolex](https://repolex.ai).

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
rlex download bottlepy/bottle-inject
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 321d7f45be70a2afb412c2d93022151e454f4757
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 321d7f45be70a2afb412c2d93022151e454f4757
│           └── chunk-001.nq.gz
├── blob
│   ├── 1b5125ccca3bea5b6b8edff33d0dc79bd4f0ecf5.nq.gz
│   ├── 21ba1e2ecd55c9b066b1e369eb8d3f67f21c946f.nq.gz
│   ├── 26a5f2f50f7de3549527a035f7c7e3834ea6c570.nq.gz
│   ├── 463c8ae890f24db3f57345653d8f9e40c05f796b.nq.gz
│   ├── 5f3e8de3a2e3321bfb79e60f62d3fa2daaa6aefe.nq.gz
│   ├── 774b8b4fb6039490f6972d3a86c569b1cdef0932.nq.gz
│   ├── b3f768abc899278f18f3ce5a727694b33e2ce742.nq.gz
│   ├── b8d7c5842e70dc622d06d6e2298333a5686076f3.nq.gz
│   └── c0dcfb92b7b12a67f7ef284bac85a811db3dcf0a.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 321d7f45be70a2afb412c2d93022151e454f4757.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 17 files
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

[bottlepy/bottle-inject](https://github.com/bottlepy/bottle-inject)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
