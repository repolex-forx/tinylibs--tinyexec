# Repolex Knowledge Graph of tinylibs/tinyexec

RDF knowledge graph data for [tinylibs/tinyexec](https://github.com/tinylibs/tinyexec), parsed by [repolex](https://repolex.ai).

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
lexq download tinylibs/tinyexec
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 53d193454ee2cbab6b3869ccc7b20883debad9c7
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 53d193454ee2cbab6b3869ccc7b20883debad9c7.nq.gz
│   └── repolex
│       └── 53d193454ee2cbab6b3869ccc7b20883debad9c7
│           └── chunk-001.nq.gz
├── blob
│   ├── 11fd0902fbe8458b0e19c1bf336eb00f54ae4af4.nq.gz
│   ├── 149dafd823221074733f1135a883098d1e842424.nq.gz
│   ├── 154816145e67841df7357b5d0715532a25ba760b.nq.gz
│   ├── 219fdccf4d1c949208b4cbc5605d66a6e4a0ed72.nq.gz
│   ├── 424e4afb9946b3daa0f42b85ab971b03e1600d8e.nq.gz
│   ├── 4884aa9a5a1f39e7c8839015f33c46c1e6fe89eb.nq.gz
│   ├── 558eb6a0897bad7337e0a562c471965759cff6c0.nq.gz
│   ├── 61bb30e8bd2fe10690f7be3164c55151f2d88e90.nq.gz
│   ├── 6750b09ccdb492d959134b69fc3bc2dcf6693cc4.nq.gz
│   ├── 6c0e900f03db604f13fcca8656ad01767885c8d8.nq.gz
│   ├── 79f9c7d282efd479b5d9838d5b02a65121a7cc6a.nq.gz
│   ├── 83a70a0dba6fee91ba30a28a5e980315de0b4117.nq.gz
│   ├── 875da5157b245f224ea95d4f25472bab89b89a9c.nq.gz
│   ├── 8b35d4b37a6eb1e0a25aacf1afecf754c337ca95.nq.gz
│   ├── a18586ba9bce8f60e8302244b6a03d57a8ea97d4.nq.gz
│   ├── a2a0cd194d5bf270f93da4880b37445c941a61f2.nq.gz
│   ├── af1dc68c8e15eb1631abac77d5a2781fe5e969d5.nq.gz
│   ├── b92ef59405b936bd035ac1e2dbf5a48093fb9f14.nq.gz
│   ├── cde4ec3092d9384a02f629679ae3ff8986054e17.nq.gz
│   ├── da9c516dd744b6c88dd8c91f58f7bcf8f7e8341b.nq.gz
│   ├── e5264cea16c7607c0df57a0b6be7a84a8f3c5d30.nq.gz
│   ├── e86b74f612a6d735bd652cc5219fe59b5975e0f2.nq.gz
│   ├── f6196354e7859eacf2f37bf87e55c64199c91579.nq.gz
│   └── fba42606cdc66832b70eb8b3cdd8c169052624f5.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 53d193454ee2cbab6b3869ccc7b20883debad9c7.nq.gz
├── filetree
│   └── 53d193454ee2cbab6b3869ccc7b20883debad9c7.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 34 files
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

[tinylibs/tinyexec](https://github.com/tinylibs/tinyexec)

---
*Parsed on 2026-09-16 by [repolex](https://repolex.ai)*
