# Repolex Knowledge Graph of UKPLab/emnlp2026-review-quality-estimation

RDF knowledge graph data for [UKPLab/emnlp2026-review-quality-estimation](https://github.com/UKPLab/emnlp2026-review-quality-estimation), parsed by [repolex](https://repolex.ai).

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
rlex download UKPLab/emnlp2026-review-quality-estimation
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── e434df47c95053740085f6936e90017a52ac3107
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── e434df47c95053740085f6936e90017a52ac3107
│           └── chunk-001.nq.gz
├── blob
│   ├── 02151db313722e26d27d18c871207fb88b41aa07.nq.gz
│   ├── 0d0948e3281a23a6c098492cc1edaffb3000391c.nq.gz
│   ├── 0d9360dc35d158ea1ccd025d9520994762579eec.nq.gz
│   ├── 10931caf8a604d49070dd4fd8ae8b8799d3a0841.nq.gz
│   ├── 120c6893b8af8f69dddc51b2734ed561b78c6091.nq.gz
│   ├── 23fb2a533f791582f8d94fe4f4aa6419862dbf25.nq.gz
│   ├── 26aac1e14cdf9f077999108d2a5ac01e332b07c4.nq.gz
│   ├── 272cc21976c6ec76d771b077166ec6a43f1cad14.nq.gz
│   ├── 3158c6a7ce8b861c99e3ae36f97b107e1bf65f23.nq.gz
│   ├── 4494992e95a890d760734ccf84e8f96ba53b132e.nq.gz
│   ├── 460f4a85331559ec275adcfb252f74295dcc56d6.nq.gz
│   ├── 4cef27e61ea9ac6f982e68a89dcb12432298bb71.nq.gz
│   ├── 517518a2cb4c9616e7ec4bf3712d873f8a84d697.nq.gz
│   ├── 56cca75917f5bb5f9befcc2794a7ce1eff269781.nq.gz
│   ├── 663745cd0382d6c4c4413c93a42df9888a7ab165.nq.gz
│   ├── 74e1fc296837cfe6c8fbd6aebf30bfe2b9407e09.nq.gz
│   ├── 7989ddb14e8e72b43665869676bd12d5e99eb03a.nq.gz
│   ├── 7fc114a4791d1901f6bdf508dd27de7b0c6ec5f4.nq.gz
│   ├── 83140cf2665ec3ee1cc02528f7b485294199cd87.nq.gz
│   ├── 8485ec439a58f292e0f3a7680a165d14e5b12080.nq.gz
│   ├── 8a32ee34b1603953ed79a91dec01453f67fb93c4.nq.gz
│   ├── 95d35d2e2ab07dd114394123fbdbe7b8f6836ce6.nq.gz
│   ├── 9b4e0eb8c3d0cff034b96f5f88d806d657cb18fb.nq.gz
│   ├── 9ccc7363dcc9155dec920e64a9820737d3fff0e3.nq.gz
│   ├── b288a9c3aae2426a3f74de52a91cef92d4735ce9.nq.gz
│   ├── b8b776fccf04790f5ae3ede0c20efad0f9c30f64.nq.gz
│   ├── cc98b6933cd0df2705fd39225f24282258cd3685.nq.gz
│   ├── ccd7f58db90362e0d6d83ad2cfd2da30fc24b9b9.nq.gz
│   ├── de58b2dbb9398e3d5034fd9c4b6cc66fa3ff0f1b.nq.gz
│   ├── e12e36d254e8952105d249c8ec6ea0e13cc37eaa.nq.gz
│   ├── e9a8da21c782754b961d41d85b4e97af4213e6e9.nq.gz
│   ├── ea6d05ea8f9d193059c6b06318dbcc5229e7b33a.nq.gz
│   ├── f6f9333d52c5124a7932bd00926254b493a81fb1.nq.gz
│   └── ff0d806bf5bc3fd03118022f03f495c86bfd8bf8.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── e434df47c95053740085f6936e90017a52ac3107.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 41 files
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

[UKPLab/emnlp2026-review-quality-estimation](https://github.com/UKPLab/emnlp2026-review-quality-estimation)

---
*Parsed on 2026-11-08 by [repolex](https://repolex.ai)*
