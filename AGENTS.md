# AGENTS: BurgoyneBlue

<project_source project="delongpa" file="AGENTS" format="hybrid-xml-markdown" />

The session procedure for any agent working in this project, whatever its role. What you may and may not do is in
`SOUL.md`. How to talk is in `STYLE.md`. How to do the recurring tasks is in `SKILLS.md`. A role's own profile
adds its own rules on top of these and never loosens them.

## Load order

<load_order>

Read these before you say anything to Jeremy:

1. `WORKFLOW.md`: how scripting work moves between profiles, the gate, and the task conventions.
2. `SOUL.md`
3. `STYLE.md`
4. `SKILLS.md`
5. `MEMORY.md`
6. `series/SERIES.md`, if it exists.

</load_order>

## What is here

<what_is_here>

| Path | What it holds | Who writes it |
|---|---|---|
| `WORKFLOW.md` | Scripting process | Process change only, with Jeremy's approval |
| `knowledge/` | Reference material the scripting profiles read | Process change only |
| `templates/` | Starting files the scripting profiles copy | Process change only |
| `series/SERIES.md` | Series title, theme, audience, and each episode's entry and Pipeline line | The Artist creates it; the Reviewer ticks boxes |
| `series/VOICE.md` | Jeremy's voice, in his words | The Writer, by interview |
| `series/episodes/<folder>/` | One folder per episode: stage outputs `01-`…`04-`, `reviews/`, `head-log.md` | The stage profiles, the Reviewer, the Head |
| `series/head-pending/` | Head logs for episodes whose folder does not exist yet | The Head |

Episode folders are named `s<SS>e<EE>-<slug>`.

</what_is_here>

## Repository

<repository>

This project is the git repository `git@github.com:jdelon02/delongpa-channel.git`. Committing and pushing are
Jeremy's call, and pushing publishes work outside this folder. Never force-push, and never delete or rewrite
history (`SOUL.md`, rule 3).

</repository>

## Two workflows

<two_workflows>

**Scripting (defined).** Four stages, each with its own profile: Artist, Architect, Writer, Wizard, gated by the
Reviewer and coordinated by the Head Scriptwriter. Jeremy talks to each stage profile directly, because the
scripts are his. `WORKFLOW.md` is the authority. Do not restate or change it.

The profiles' source is the `scriptwriting` repo (`/Users/jdelon02/Projects/scriptwriting/profiles`). They are
installed as Hermes profiles (`script-artist`, `script-architect`, `script-writer`, `script-wizard`,
`script-reviewer`, `script-head`) and started against this folder, for example
`script-artist chat --in /Users/jdelon02/Projects/delongpa`. That launch syntax comes from the scriptwriting
docs, where it is marked untested. Each profile's live memory is in its own Hermes home, not in this folder.

**Video production (not defined).** Everything after `Scripted` (filming, editing, thumbnails, titles,
publishing, and whatever else it turns out to need) is meant to be run by agents with human checkpoints. None of
it has been designed. Do not invent stages, tools, or checkpoints, and do not treat `Filmed` and `Published` as
anything more than boxes Jeremy ticks. If a request needs this workflow, say it is not defined and follow
`SKILLS.md` (`route`).

</two_workflows>

## Where work comes from and where you talk

<where_work_comes_from_and_where_you_talk>

Work is assigned as Multica issues, and all communication happens in them (see `STYLE.md`). The `multica` CLI is
installed here, and `multica issue --help` lists its issue commands. `WORKFLOW.md` ("Orchestrator mapping") maps
the abstract states to Multica's statuses: `In Progress`, `In Review`, `Done`, and `Blocked`. Use only what that
table confirms, and do not invent status names, labels, or IDs. What it lists as unverified (run triggers,
dependency links, return labels) stays unverified.

If you have no way to reach Multica, say so. State the exact actions you would take instead of claiming them
(`SOUL.md`, rule 6).

</where_work_comes_from_and_where_you_talk>

## Session steps

<session_steps>

1. **Read the issue.** Know exactly what you were asked to do, for which episode or item, and who assigned it.
2. **Read the state** from the files and the issue history. Say "unknown" where there is no evidence.
3. **Do only what was assigned,** within `SOUL.md`. If the work belongs to a role's profile (for example
   interviewing Jeremy for script content), do not do it yourself: say which profile to start and how.
4. **Comment on the issue** in the shapes in `STYLE.md`: state first, then what Jeremy needs to do next.
5. **Memory.** Update `MEMORY.md` only if Jeremy told you a durable fact about himself or his work, or corrected
   you. Follow the rules at the top of that file. Never write episode content there.

</session_steps>

## What never lives here

<what_never_lives_here>

Secrets, API keys, and credentials. Never write them into any file in this folder.

</what_never_lives_here>

## Code discovery and knowledge tools

<code_discovery_and_knowledge_tools>

Use these before grep/find or bulk file reading, in any checkout that provides them. A missing
index directory means skip that tool; indexing is Jeremy's decision, never yours.

### CodeGraph

- If `.codegraph/` exists at the checkout root, ask it first: the `codegraph_explore` MCP tool
  (when available) or `codegraph explore "<symbol names or question>"` in the shell. One call
  returns the relevant symbols' source and the paths between them.
- After committing substantive changes, run `codegraph sync` to keep the index current.

### code-review-graph

- If `.code-review-graph/` exists at the checkout root, use its MCP tools:
  `detect_changes_tool` (risk-scored change review), `get_impact_radius_tool` (blast radius before
  modifying), `get_affected_flows_tool`, `query_graph_tool` (callers/callees/imports),
  `semantic_search_nodes_tool`, `get_architecture_overview_tool`, `get_review_context_tool`
  (token-efficient snippets), and `refactor_tool`.
- After committing, run `code-review-graph update` to refresh the graph.

### okf knowledge bundle

- If a `docs/knowledge/` bundle exists, discover concept context with `okf search`, `okf show`,
  and `okf backlinks` before reading raw documentation files.
- Run `okf validate docs/` after editing bundle documents, and `okf index docs/knowledge/` after
  adding or moving them.

</code_discovery_and_knowledge_tools>
