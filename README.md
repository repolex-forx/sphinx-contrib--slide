# Repolex Knowledge Graph of sphinx-contrib/slide

RDF knowledge graph data for [sphinx-contrib/slide](https://github.com/sphinx-contrib/slide), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-contrib/slide
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── d4356365c64ca04a7f4bd65667912392072b058a
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── d4356365c64ca04a7f4bd65667912392072b058a
│           └── chunk-001.nq.gz
├── blob
│   ├── 01112a0e0d51d10bfddb8ef1f8d572fb3f9f4110.nq.gz
│   ├── 1e32f036969b0fd3aa501d49efc9d1ff7162915c.nq.gz
│   ├── 35d34fc53bde73a52472b7e1cfce9b183d7aaa66.nq.gz
│   ├── 45c819db5906251be055704d5095388b059c0ab0.nq.gz
│   ├── 45dd5f5b51e10661a6b6699e050c4ab23d721804.nq.gz
│   ├── 4a690e94e5e12251ca639f5882367a32afe4087e.nq.gz
│   ├── 543ff5c1c5c3b78750e631d4108aa92ccd47ca96.nq.gz
│   ├── 59076bc8a66cee80e64fcabfc64fae9a2dcbee20.nq.gz
│   ├── 6deafc261704e20369c0983af88042e502ae4880.nq.gz
│   ├── 7c45b4157c252c68a601d54950b7cef9c8343db5.nq.gz
│   ├── 821be5ef7d7f5e3faa74beb3b6b72205eeab3c59.nq.gz
│   ├── 94cd48322f92fa9e270bc2958ecfda9e9e1e7068.nq.gz
│   ├── 96b6f1c49e580154f6719454f17562510576afe0.nq.gz
│   ├── 97ceb018c2664cdbebd5c88791106ebca0a9c9ff.nq.gz
│   ├── 98e1629c4b2cf307c847b62ed67d93685b653568.nq.gz
│   ├── ac8393474a0855e66d45baa486e81a65574037d9.nq.gz
│   ├── b7091784216f0b3de139b68716ace82f9c41ea14.nq.gz
│   ├── ee912d0b2627b9e1c0085b66918bf5d1a8ccebab.nq.gz
│   └── fc6f740e7cc424e374bb01f166d16b5c89578f55.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── d4356365c64ca04a7f4bd65667912392072b058a.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 27 files
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

[sphinx-contrib/slide](https://github.com/sphinx-contrib/slide)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
