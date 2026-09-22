---
type: playbook
title: Repository-wide OKF indexing
description: Search repository Markdown while keeping canonical files in their original locations.
tags: [delongpa, okf, indexing]
---

# Repository-wide OKF indexing

Root instructions, knowledge, templates, series, episode artifacts, and documentation stay
in their original locations. This mirrors `../scriptwriting/scripts/sync_knowledge.py`:
Git discovers tracked and non-ignored new `.md` files throughout the repository, excluding
hidden runtime trees and `docs/knowledge/` itself. Curated documents in the bundle are
already searchable and are not copied again.

## Refresh and search

From the repository root, after cloning or changing Markdown:

```bash
python3 scripts/sync_knowledge.py
okf search docs/knowledge --text "Grand Payoff"
okf show docs/knowledge repository/AGENTS
okf validate docs/knowledge
python3 scripts/sync_knowledge.py --check
```

The sync copies source bytes into `docs/knowledge/repository/<original-path>` and runs
OKF indexing and validation. Generated copies are ignored by Git and rebuildable.
The `.sources.json` manifest tracks owned copies; deleted sources remove only their
generated copies. Unmanaged bundle files are preserved. No commit hook is required;
run the sync explicitly. `okf index` alone does not refresh copies, and `--check` only
checks copy freshness, without writing or re-running OKF validation.

## Authoring

Always edit the original identified by `source_path`, never a generated copy. New
source Markdown needs YAML frontmatter with a `type` field. Include `title`,
`description`, `tags`, and `source_path` as well. Existing content below the metadata
stays intact; agent entry points such as `AGENTS.md` and `SOUL.md` remain at the root.

Source files named `index.md` and `log.md` become `index.source.md` and `log.source.md`
in the generated bundle because OKF reserves those filenames. Links to these source
names may need adjustment. Generated navigation stays inside the bundle.
