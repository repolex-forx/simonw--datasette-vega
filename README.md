# Repolex Knowledge Graph of simonw/datasette-vega

RDF knowledge graph data for [simonw/datasette-vega](https://github.com/simonw/datasette-vega), parsed by [repolex](https://repolex.ai).

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
rlex download simonw/datasette-vega
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 6fe66c4c9d0dba0a6eb636583914d2ed7d3d72a9
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 6fe66c4c9d0dba0a6eb636583914d2ed7d3d72a9
│           └── chunk-001.nq.gz
├── blob
│   ├── 1546b2f051a58a748f23669eea33bbff990f38b5.nq.gz
│   ├── 200d19fbb451b15558ec2670fc1661a54544052f.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 45d40ddbc8526348ae4bafcebcd4f293198267a7.nq.gz
│   ├── 8dc87221bb7467e643e928884adf7c622423bbbf.nq.gz
│   ├── 969c2a289b7d5e274bb6c39cfcc5aa78954445c6.nq.gz
│   ├── 983aee4a59701d47c0b2601cb30ce6c67ba6585d.nq.gz
│   ├── 98adc8f03d9256039fbcd68dc5f54dd1dfb9a605.nq.gz
│   ├── a11777cc471a4344702741ab1c8a588998b1311a.nq.gz
│   ├── a77cd7fed3a4391c60947da1022a68caea72a251.nq.gz
│   ├── ac80b52c45649e598e297ea9f27162ee5e1ab4f7.nq.gz
│   ├── b617a0199874e4010c446e7bf7034933f7fa99fa.nq.gz
│   ├── b634a8729b5a2064d88f8ccadd58558e56c3cf3f.nq.gz
│   ├── d94e3ee0eb218ad41fd5392e80564919aac13681.nq.gz
│   ├── ef19ec243e739479802a5553d0b38a18ed845307.nq.gz
│   └── efbcbeba3199e6cd5cb462d8a0e26b005a23cecd.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 6fe66c4c9d0dba0a6eb636583914d2ed7d3d72a9.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 24 files
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

[simonw/datasette-vega](https://github.com/simonw/datasette-vega)

---
*Parsed on 2026-10-18 by [repolex](https://repolex.ai)*
