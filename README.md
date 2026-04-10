# Repolex Knowledge Graph of jshttp/basic-auth

RDF knowledge graph data for [jshttp/basic-auth](https://github.com/jshttp/basic-auth), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [lexq](https://github.com/repolex-ai/lexq) query tool using [uv](https://docs.astral.sh/uv/getting-started/installation/).

If you have uv installed, just copy/paste this into your terminal:

```bash
uv tool install git+https://github.com/repolex-ai/lexq
```

This installs lexq onto your system, in your user context. Verify the install:

```bash
lexq --help
```

**lexq is designed to be used primarily by LLMs in a terminal.** Start up your favorite LLM and ask it to use the lexq tool. It's that easy!

To load this repo's data:

```bash
lexq download jshttp/basic-auth
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── bde0bac8ba99f5d461a339cb6b8a598a0586d699
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── bde0bac8ba99f5d461a339cb6b8a598a0586d699.nq.gz
│   └── repolex
│       └── bde0bac8ba99f5d461a339cb6b8a598a0586d699
│           └── chunk-001.nq.gz
├── blob
│   ├── 01bd8dc38f2ead10727c60b89d48f40be8f610b5.nq.gz
│   ├── 1eece14ad8cb98de2093fac5eef5ccee89472ff8.nq.gz
│   ├── 2c44a01012ddd3287cd9e9fbed320ffe1b8894aa.nq.gz
│   ├── 5f3d758bc62e742b17c4ae3de9124f6761b7bb62.nq.gz
│   ├── 62562b74a3b5a79e82ca417b02e0f597d85f5e2f.nq.gz
│   ├── 84a486374839e3ec338b67cabaaf76343d600e7d.nq.gz
│   ├── 89041f613a2c9dc159c50c9edaf0d21534df34cd.nq.gz
│   ├── 9106e646ed0f6082e36d5f8c1d34a95e649329e0.nq.gz
│   ├── 9808c3b2b6602da61eb4afcb4caf33368e3e2bd4.nq.gz
│   ├── c9fe2216931ba87eece61686c2980522865e3201.nq.gz
│   └── dc0f8678bf09b6e0202d57f89b8d5472c097acda.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── bde0bac8ba99f5d461a339cb6b8a598a0586d699.nq.gz
├── filetree
│   └── bde0bac8ba99f5d461a339cb6b8a598a0586d699.nq.gz
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

## Source repository

[jshttp/basic-auth](https://github.com/jshttp/basic-auth)

---
*Parsed on 2026-04-10 by [repolex](https://repolex.ai)*
