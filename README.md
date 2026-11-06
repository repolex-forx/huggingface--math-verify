# Repolex Knowledge Graph of huggingface/math-verify

RDF knowledge graph data for [huggingface/math-verify](https://github.com/huggingface/math-verify), parsed by [repolex](https://repolex.ai).

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
rlex download huggingface/math-verify
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── ba3d3aaff23b3f4cac7a14672b4f6e293d97c98b
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── ba3d3aaff23b3f4cac7a14672b4f6e293d97c98b
│           └── chunk-001.nq.gz
├── blob
│   ├── 1ca28c33e767438d66fe42a2d93131becf131f70.nq.gz
│   ├── 2012f8cc314537aecdc7bc0c58b401c398633b25.nq.gz
│   ├── 247e87d7cbae44a22ef225f5cffd5e7e947fbb4e.nq.gz
│   ├── 2b4876201593f4f219bedd57a36e2c815a13f02d.nq.gz
│   ├── 2f4c68f9b1c83892e2924c95cb53ccf4a6a76069.nq.gz
│   ├── 3d41fbf2f4afcc91d6292fc72ef16a8eb7b07bd7.nq.gz
│   ├── 4261ff9d028a2edb452ea8741e95b7ab7cffce28.nq.gz
│   ├── 4769efbae622c6d12665132e096d495d3e660841.nq.gz
│   ├── 479cdd0de2c53bfbbe2ff20b9e569d97a1882b5d.nq.gz
│   ├── 55254328b3a9dd0384705aa51d3684e97dddc3bb.nq.gz
│   ├── 6100a1c00584e93ddd8fc5dfaae515b0dc87e9c7.nq.gz
│   ├── 65cd8a38dbe92490bb1e701f76364765e67eeb01.nq.gz
│   ├── 679b3ba44dff98daa77b5739eddf817a83eba026.nq.gz
│   ├── 6aaf048f33762569bd591f953146d3ec29fc18d3.nq.gz
│   ├── 6fea65c2ec5a37ce8cf77c894e5c2b2fd0642046.nq.gz
│   ├── 7b87751456f97ab6375a0c775605eac14d70df05.nq.gz
│   ├── 8193e2fdf4869bd99ee740f34620debcd15d604e.nq.gz
│   ├── 883098a5ba972155c20812e0e0ba5da6f31d2c78.nq.gz
│   ├── 9c5c0e16aec35457f31c0c3bf6d0df86acdea4a5.nq.gz
│   ├── aaecbecb2c367781a3cdf8300015513032cb6e96.nq.gz
│   ├── b3ac445511201dfd33e2b146f380ad6600a74d0e.nq.gz
│   ├── d5bed5a00d92bf011ec0f2d68883ecc79b8fe749.nq.gz
│   ├── d771aca3e2f44f962d806953ef3ccb506c974c85.nq.gz
│   ├── da2d71afde77257b4b23a876a04222cbd8daaf9e.nq.gz
│   ├── dc800aa5bf9280fa4ab300e20ebc36c0f4638522.nq.gz
│   ├── defcc19665b556d9104c596ab8b5300a56b83b3a.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e70bf26d63d1f75b4d0f5e9ff691dd449a8d75cf.nq.gz
│   ├── e9ea518a3fd52bc8f4c763d034ceeae97074b0ad.nq.gz
│   ├── ec74c0a3b72349ca7d63332b94dbd95920ccc42c.nq.gz
│   ├── eebcf1e75c7f5f638506511191ac66d13c3d224e.nq.gz
│   ├── ef71bd0d784d2fd097f0d2fc20f6a96b00c370e7.nq.gz
│   └── fea3be5881ed210abc849b184cf91bed35e69629.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── ba3d3aaff23b3f4cac7a14672b4f6e293d97c98b.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 41 files
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

[huggingface/math-verify](https://github.com/huggingface/math-verify)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
