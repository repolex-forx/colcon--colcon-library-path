# Repolex Knowledge Graph of colcon/colcon-library-path

RDF knowledge graph data for [colcon/colcon-library-path](https://github.com/colcon/colcon-library-path), parsed by [repolex](https://repolex.ai).

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
rlex download colcon/colcon-library-path
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 8bf9381308fc1eb71fa9e187a88d90f2e0960c10
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 8bf9381308fc1eb71fa9e187a88d90f2e0960c10
│           └── chunk-001.nq.gz
├── blob
│   ├── 094694993f1462cbee1371e4f09eef38fda7535d.nq.gz
│   ├── 0f17157ed42b486a0c57cbffddd97987a4844e6b.nq.gz
│   ├── 162379c1a025c369ec1b1a394498c6dbd72e41a4.nq.gz
│   ├── 3624ba34aaed6d1a36184d17f6583dc246b2d181.nq.gz
│   ├── 506ab13572514a740402cd04a1d35efd2d16e72a.nq.gz
│   ├── 8f9fa87943276ba70c779565de7e2081e27f9aab.nq.gz
│   ├── 9107e5ffc36f53550698d931188a054c23517374.nq.gz
│   ├── aaaf232408283e06ae0c8385774dbfbb5e87816c.nq.gz
│   ├── ae1aaca964f1954de69523ea9be380b14fef9633.nq.gz
│   ├── bd7c8693b373f16474a10254e75b502ef8389f27.nq.gz
│   ├── d645695673349e3947e8e5ae42332d0ac3164cd7.nq.gz
│   ├── dffe460f162da9929178a7ce342532e7ba896425.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e82fd0b0abbf1472480d19d468efe7819276e80d.nq.gz
│   └── f6c6ecc368d4ed6cf72de361d28e6c2522ea3640.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 8bf9381308fc1eb71fa9e187a88d90f2e0960c10.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 23 files
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

[colcon/colcon-library-path](https://github.com/colcon/colcon-library-path)

---
*Parsed on 2026-10-17 by [repolex](https://repolex.ai)*
