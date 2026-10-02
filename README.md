# Repolex Knowledge Graph of NousResearch/hermes-plugin-supermemory

RDF knowledge graph data for [NousResearch/hermes-plugin-supermemory](https://github.com/NousResearch/hermes-plugin-supermemory), parsed by [repolex](https://repolex.ai).

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
rlex download NousResearch/hermes-plugin-supermemory
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── d798057e93c85198121cfd6ebf70a529559d38e6
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── d798057e93c85198121cfd6ebf70a529559d38e6.nq.gz
│   └── repolex
│       └── d798057e93c85198121cfd6ebf70a529559d38e6
│           └── chunk-001.nq.gz
├── blob
│   ├── 00f2d38d8063d0c6b219c0081e51888063b0c55e.nq.gz
│   ├── 2dec58811051262f41b4490fd5577d160ae717ab.nq.gz
│   ├── 5f763782deab5e35a1c55bec7e1b42a5371dffb2.nq.gz
│   ├── 75410e73319c72cd3e991a501c5455eb78f38375.nq.gz
│   ├── afb2cf0f483cbb81b21adcadfde67d9b8fa423d5.nq.gz
│   ├── b253c1962d6089ba37ce6e509a811f46e935247a.nq.gz
│   └── fa265a6636f5ba2869044f6a5ca89e20f97abd8e.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── d798057e93c85198121cfd6ebf70a529559d38e6.nq.gz
├── filetree
│   └── d798057e93c85198121cfd6ebf70a529559d38e6.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 15 files
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

[NousResearch/hermes-plugin-supermemory](https://github.com/NousResearch/hermes-plugin-supermemory)

---
*Parsed on 2026-10-02 by [repolex](https://repolex.ai)*
