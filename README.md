# Repolex Knowledge Graph of scrapy/scrapyd-client

RDF knowledge graph data for [scrapy/scrapyd-client](https://github.com/scrapy/scrapyd-client), parsed by [repolex](https://repolex.ai).

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
rlex download scrapy/scrapyd-client
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── c6aa9d58170259d4a76115dacd605642dbd51da2
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── c6aa9d58170259d4a76115dacd605642dbd51da2
│           └── chunk-001.nq.gz
├── blob
│   ├── 0535b33f3ea07023addd2fa1bca3c32cb36c58f3.nq.gz
│   ├── 0abbd108176dd30c882633e57a8899a6fe7ba6fa.nq.gz
│   ├── 13515c825a27ec8abae93dd23193c21ebb69cf4c.nq.gz
│   ├── 13528cff5ee67fbbdd24ec949e348270a91b893a.nq.gz
│   ├── 13f733ca954bd01826df0f32d877c7b260a5bf5b.nq.gz
│   ├── 171bb2cfe0a90c96abe99672123a9c3d0bce1e9d.nq.gz
│   ├── 3237f1bc64e40fa196046ad45904ef184ebe60fc.nq.gz
│   ├── 48c5de9b60c4b15089a7fd53a36d259185a3c1ce.nq.gz
│   ├── 4e71b361374cb823bafa0881181f2e6400c33848.nq.gz
│   ├── 50ec8c8cb204a8ea6f6b9d097a9b5adb2538912d.nq.gz
│   ├── 52175095058383a7de2e40dc7bd8fb4656ea875c.nq.gz
│   ├── 68ccf976261e2eb7a928b2e6b59cd2ffed86551a.nq.gz
│   ├── 73cdd17fe28a7242ab0b886c37e66f042e28c1ec.nq.gz
│   ├── a433df2823b39978b7eafe1589a3da938de91099.nq.gz
│   ├── a6407f685f6ce0fef0cee597904ffc329415878e.nq.gz
│   ├── af16ae6c6a43025f967c5308070367c967132c55.nq.gz
│   ├── b0fa1f093ff99c4ddb7663314b9d1ebe4aacc1a1.nq.gz
│   ├── b15b1c5a3e78b9240370c02644d279b904089b31.nq.gz
│   ├── b87c0af03887356872acdbb60bdd4676437f1d8a.nq.gz
│   ├── ba846e6e0451974ddb002f65eab802f50c51da6c.nq.gz
│   ├── c80dcbb8a8e1cd9e00b542c2f1498cf5a4d459bf.nq.gz
│   ├── d2f4ad3189ca9ac0881e8f67382a919198538101.nq.gz
│   ├── dabbaa02bf80fc226feb6a0e60a7f6510bbf51fe.nq.gz
│   ├── dc0bbf0b36eaa95569b3a582c75fc7e218772cae.nq.gz
│   ├── dea0b231171dce2444b69af74a56c125849a171d.nq.gz
│   ├── df8d836356e060059e00374ff5c89e3740ae61ac.nq.gz
│   ├── efabe68d2fb490b5c88223c0dbca30fea9f162a4.nq.gz
│   └── f2d07d7daaf0aa3d06420090e594b95fdeb28813.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── c6aa9d58170259d4a76115dacd605642dbd51da2.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 36 files
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

[scrapy/scrapyd-client](https://github.com/scrapy/scrapyd-client)

---
*Parsed on 2026-10-12 by [repolex](https://repolex.ai)*
