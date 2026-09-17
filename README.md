# Repolex Knowledge Graph of rbarrois/tdparser

RDF knowledge graph data for [rbarrois/tdparser](https://github.com/rbarrois/tdparser), parsed by [repolex](https://repolex.ai).

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
lexq download rbarrois/tdparser
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── b1ad88e0515253846ffc208e8960c62584dd0f86
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── b1ad88e0515253846ffc208e8960c62584dd0f86.nq.gz
│   └── repolex
│       └── b1ad88e0515253846ffc208e8960c62584dd0f86
│           └── chunk-001.nq.gz
├── blob
│   ├── 0dc0e51a0aedfd4e71817871173fd852a5105b0e.nq.gz
│   ├── 100b93820ade4c16225673b4ca62bb3ade63c313.nq.gz
│   ├── 1506552a9d810b479485fe96f90281cd18efa08e.nq.gz
│   ├── 19a98c6c5bd61abf6489d507f60dbb5b4adfe1b2.nq.gz
│   ├── 24d64eb89ebf2e47155fc7c2dac3ba7d49c0052a.nq.gz
│   ├── 3594ca0f42cc73ffb369fdb3fa75d7ca9f35d163.nq.gz
│   ├── 36ab6c55df98c514da25f4a24ce8d1019877d3d2.nq.gz
│   ├── 504d59e853ff999818257343ec0f659ff637a4b8.nq.gz
│   ├── 5c1db992af797ed999f595d3387a0b49a4bc81b1.nq.gz
│   ├── 5d285f99aa5a436c3bf8217eb0483a87979e71d8.nq.gz
│   ├── 5e3014bddfd7009b75cf2179d89d0eef6323a56b.nq.gz
│   ├── 75a6ad9a4c10b4c37a442304ac6dc796ff367943.nq.gz
│   ├── 8006a8642bb4b9f80efcf5b491458fb1db45807a.nq.gz
│   ├── 884af0ec934519c07a86eda91c91deab60366e14.nq.gz
│   ├── a7cea9649c9f02c46ac2d8ea1701bf39412b147d.nq.gz
│   ├── c1695eb40cac73588dbc5b11acdaeafffb07eab9.nq.gz
│   ├── cd38ffc7aa924054e97758030a9d39284a7b1378.nq.gz
│   ├── d16f2b030316daf90f27a672a8b77380afe285b9.nq.gz
│   ├── d1c3da219d1f1150c97943c31314d94f42d2aad8.nq.gz
│   ├── d67e2022d4271f33ba4ed7225487748b305dac12.nq.gz
│   ├── de152208eb9b6a988b07340c6aaf00da25b87273.nq.gz
│   ├── de1d49e3a24a561f55516056c53028dffb92f532.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e8f8aecc612f680db429f0dc0bf9135953755f97.nq.gz
│   ├── f268a1733919026bee91b7589707f08202e5de2f.nq.gz
│   └── f66b0fc94075a66bc4c43f170466999da7087dc5.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── b1ad88e0515253846ffc208e8960c62584dd0f86.nq.gz
├── filetree
│   └── b1ad88e0515253846ffc208e8960c62584dd0f86.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 36 files
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

[rbarrois/tdparser](https://github.com/rbarrois/tdparser)

---
*Parsed on 2026-09-17 by [repolex](https://repolex.ai)*
