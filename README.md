# Repolex Knowledge Graph of kivy/kivy-launcher

RDF knowledge graph data for [kivy/kivy-launcher](https://github.com/kivy/kivy-launcher), parsed by [repolex](https://repolex.ai).

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
rlex download kivy/kivy-launcher
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── a2f223f1458ffa631b08054f64a71fa5fb234015
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── a2f223f1458ffa631b08054f64a71fa5fb234015
│           └── chunk-001.nq.gz
├── blob
│   ├── 0d4f27272bb23b9d734476ca695fc328f521b5c2.nq.gz
│   ├── 2625dd4f26abe7cf9e7aa0bfca6beeb32595b691.nq.gz
│   ├── 2838d5d5f024bc57e71032092c0ee75848d6a141.nq.gz
│   ├── 2e81b3c6d8e01ca3739b484678c0104f43fb00cd.nq.gz
│   ├── 3f991c9b3ee80d3c78efdbdcc33238f64b15e881.nq.gz
│   ├── 418796e58c3cb5ea259e6fc59a52000dca62660c.nq.gz
│   ├── 48ad3bc1ea1d61075a8a77e5425bc7fc5b1dee11.nq.gz
│   ├── 4fb7cd667020860146129add2c3c6762bc907e70.nq.gz
│   ├── 5e0d3215328a588fb721ff3cff60d66583b030ed.nq.gz
│   ├── 65fb9be3dd36ca489c03a2bd5a5216e3babbb0d7.nq.gz
│   ├── 66922b8b6d17c7c44b617c18a220331dec292c70.nq.gz
│   ├── 6a9513371a957b50eae98c8725e89ddc4668ab52.nq.gz
│   ├── 6f907b0d10d247f22bdf6d669406d33803f46ca1.nq.gz
│   ├── 7e8b0945689e0c91e31637fbaa007078e02167a0.nq.gz
│   ├── 83597cf03748e0e732b41b005e9fcef9ed078a1f.nq.gz
│   ├── 8fa3da363e9fc1a7718943afa7f5ed21448040bd.nq.gz
│   ├── 90d231af05d3a0fcc463dcad0cd6514a9364ca58.nq.gz
│   ├── 9c53d1c0c71bb18a09582a0ea0b36961b43b7435.nq.gz
│   ├── ac5a9562fbd637637048f00b8a8eb86e6dbb4f88.nq.gz
│   ├── b3abdc66411d1b8d938ee4f8c0398fc2d5814855.nq.gz
│   ├── bbcbbe7d61558adde3cbfd0c7a63a67c27ed6d30.nq.gz
│   ├── beaab3366f0de9c53ee27b2255b6687eaeac444f.nq.gz
│   ├── ca0fc23ff9ab748097fe5af62de3fb90f82b40c1.nq.gz
│   ├── cbdaf5162c1ef0761c83b3ed21a40d8a19044540.nq.gz
│   ├── cf91be86c7c9326ca4ed3f94e3b9bbea4ac5ffbb.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── fa8d599f953b162b5b81bc5b126ce536fa215e74.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── a2f223f1458ffa631b08054f64a71fa5fb234015.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 35 files
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

[kivy/kivy-launcher](https://github.com/kivy/kivy-launcher)

---
*Parsed on 2026-11-07 by [repolex](https://repolex.ai)*
