# Repolex Knowledge Graph of zarr-developers/perfcapture

RDF knowledge graph data for [zarr-developers/perfcapture](https://github.com/zarr-developers/perfcapture), parsed by [repolex](https://repolex.ai).

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
rlex download zarr-developers/perfcapture
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── ad7f11d53686be003e5b8c76b93d29303e66635a
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── ad7f11d53686be003e5b8c76b93d29303e66635a
│           └── chunk-001.nq.gz
├── blob
│   ├── 0985e121c911b631d4db44c240ac391c72cc358b.nq.gz
│   ├── 0c7603d6d7b61607a48711e65448fe5730e037f1.nq.gz
│   ├── 10fd040df573a292eab739eb5c85d4e6d0976650.nq.gz
│   ├── 23ab4eade9834f42fa24b2aca3263f187b6abfe6.nq.gz
│   ├── 2bed0f3af627f07408d004d65bffc54324b4f13c.nq.gz
│   ├── 3c53779a1e15655f19ccb10ad1a081c4915a20ee.nq.gz
│   ├── 41cb1131d8cd14318686c67a4f29fc5da650aee2.nq.gz
│   ├── 4b611f346cc0f41f8db7872dfe26c970e63b400c.nq.gz
│   ├── 68bc17f9ff2104a9d7b6777058bb4c343ca72609.nq.gz
│   ├── 7144b3e90c7ede05fbdac313ca976fdd9b7db5ce.nq.gz
│   ├── a7dddc1d4739943f8936cb8b13777515373a932c.nq.gz
│   ├── b93294dd901134bcc0ee1ab25aee73420e369257.nq.gz
│   ├── be62d86318eeec927dc6a7533cefe950e4d9db5a.nq.gz
│   ├── c49e396bf279cfafb652550f0189e05ec503d758.nq.gz
│   ├── c76f275a27ec4544474c4cea5014f1bed985d2c4.nq.gz
│   ├── c83d2404ffd4fe46defc91c5a61b6b799ea4c2dc.nq.gz
│   ├── d2a00af54e359ab412891bcfd275e181e774d7e8.nq.gz
│   ├── da78ef793d29d811dca437912d9f308880213cf1.nq.gz
│   ├── dbe9716a3302dfe8faa31a7daa63502e0d3d9907.nq.gz
│   └── dce287b38954220f4654c8a54c89ea5f1f85764c.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── ad7f11d53686be003e5b8c76b93d29303e66635a.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 28 files
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

[zarr-developers/perfcapture](https://github.com/zarr-developers/perfcapture)

---
*Parsed on 2026-10-28 by [repolex](https://repolex.ai)*
