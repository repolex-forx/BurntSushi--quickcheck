# Repolex Knowledge Graph of BurntSushi/quickcheck

RDF knowledge graph data for [BurntSushi/quickcheck](https://github.com/BurntSushi/quickcheck), parsed by [repolex](https://repolex.ai).

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
rlex download BurntSushi/quickcheck
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 458ca5c9a46a19a55a0be6d839cab17aeb216a3f
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 458ca5c9a46a19a55a0be6d839cab17aeb216a3f.nq.gz
│   └── repolex
│       └── 458ca5c9a46a19a55a0be6d839cab17aeb216a3f
│           └── chunk-001.nq.gz
├── blob
│   ├── 0857e8262116681d92f05bfb1cfbc78a53fdcdb0.nq.gz
│   ├── 0d2db889049391c8b52be9126dc342f6755adfd8.nq.gz
│   ├── 213c95660bcd3fef5d156508b6792471e473c349.nq.gz
│   ├── 22761ba7ee19a94703411264d274ae1da1d326ff.nq.gz
│   ├── 26ca84f2529838e5a0cdb2908b3cbb1b102cfb39.nq.gz
│   ├── 2c7e267cf558a91f8a527b399fce71228a5947f8.nq.gz
│   ├── 3e48bf4016a4d78072ec153bad906d49016c27b8.nq.gz
│   ├── 671a20963fc165225d04f600fc5bf3505956a5d4.nq.gz
│   ├── 68a49daad8ff7e35068f2b7a97d643aab440eaec.nq.gz
│   ├── 7386579baa0310a57f7b2278d8ac98e8a47b5726.nq.gz
│   ├── 7f9d2352fcc0dbb8c4b076269dd16a8dcc7c23dc.nq.gz
│   ├── 8491fd5f34bd1041cb1cb0143e119ec1805ea6bc.nq.gz
│   ├── a7e47e540106c31b9296084202f9bb9ef0e19cde.nq.gz
│   ├── ac566ddc6a450693e7ecaeb71f3f8d3b9f2e482c.nq.gz
│   ├── ad11ed2c242515bc8854e6ec6db7d44cb46fc8f1.nq.gz
│   ├── b42edf7579a644f790c1f9b4d462441e87ce26f9.nq.gz
│   ├── c43ac9e972599f8c89ae0f98386fd668e7e6428e.nq.gz
│   ├── d38519da288b0c9a435ac89c2ba485a057db2588.nq.gz
│   ├── e0378469ee37dbe6d04376e182ba30b1b1bc9589.nq.gz
│   ├── fa1c2a0f67cdafa00d95f45f9a3a55c6bf7c53a4.nq.gz
│   └── ffdaaba860a18572edf3499b781209531a432bdd.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 458ca5c9a46a19a55a0be6d839cab17aeb216a3f.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

14 directories, 30 files
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

[BurntSushi/quickcheck](https://github.com/BurntSushi/quickcheck)

---
*Parsed on 2026-11-22 by [repolex](https://repolex.ai)*
