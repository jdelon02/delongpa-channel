---
type: "project-instructions"
title: "AGENTS: BurgoyneBlue"
description: "Repository Markdown source: AGENTS.md."
tags: ["delongpa", "repository"]
source_path: "AGENTS.md"
---

# AGENTS: BurgoyneBlue

<project_source project="delongpa" file="AGENTS" format="hybrid-xml-markdown" />

The session procedure for any agent working in this project, whatever its role. What you may and may not do is in
`SOUL.md`. How to talk is in `STYLE.md`. How to do the recurring tasks is in `SKILLS.md`. A role's own profile
adds its own rules on top of these and never loosens them.

## Load order

<load_order>

Read these before you say anything to Jeremy:

1. `WORKFLOW.md`: the agent directory, `multica-pr-v1` lifecycle, and PR protocol.
2. `SOUL.md`
3. `STYLE.md`
4. `SKILLS.md`
5. `MEMORY.md`
6. Your own installed profile's `AGENTS.md`, `SOUL.md`, `STYLE.md`, and `SKILL.md`, resolved
   from `$HERMES_HOME`; follow that profile's load order for creative-method inputs and memory.
7. `series/SERIES.md`, if it exists.

The project files describe channel context; your installed profile describes your assigned role.
Both apply. Resolve workflow and assignment rules through `WORKFLOW.md`. A matching scripting
agent must perform its assigned role here, not redirect Jeremy to launch the same profile again.
Informational role questions follow the profile's exception to episode-specific startup requirements.

</load_order>

## What is here

<what_is_here>

| Path | What it holds | Who writes it |
|---|---|---|
| `WORKFLOW.md` | Scripting process | Process change only, with Jeremy's approval |
| `knowledge/` | Reference material the scripting profiles read | Process change only |
| `$HERMES_HOME/templates/` | Installed templates for the current role; copy file artifacts into this repo | Installer manages masters; role fills the copy |
| `templates/` | Legacy local template copies; not active profile template inputs | Historical reference only |
| `series/SERIES.md` | Creator-approved series context and episode navigation; old Pipeline boxes are historical | Assigned role within issue scope |
| `series/VOICE.md` | Jeremy's voice, in his words | The Writer, by interview |
| `series/episodes/<folder>/` | Stage outputs `01-`…`04-` and episode navigation; existing review/Head logs are historical | Assigned stage agent; Head owns navigation |
| `series/head-pending/` | Historical Head logs | Retain without updating |

Episode folders are named `s<SS>e<EE>-<slug>`.

</what_is_here>

## Repository

<repository>

This project is the content repository `git@github.com:jdelon02/delongpa-channel.git`.
Work inside the runtime-supplied checkout. For assigned scripting work, follow WORKFLOW.md's
issue branch and per-write commit/push rules; do not ask Jeremy to launch a separate session.
Git publication under that contract does not authorize uploading videos or posting as Jeremy.
Never force-push or delete/rewrite accepted history (`SOUL.md`, rule 3).

</repository>

## Two workflows

<two_workflows>

**Scripting (defined).** Artist, Architect, Writer, and Wizard work with Jeremy in this
content repository. Head Script Writer coordinates Multica issues; The Reviewer reviews and merges
their PRs. `WORKFLOW.md` contains the authoritative role → exact Multica name → UUID → Hermes
profile mapping and lifecycle rules. Use mapped UUIDs for assignment, never profile names or fuzzy names.

The `scriptwriting` repository maintains profile sources and the canonical workflow. Hermes loads
the installed profile; Multica supplies the issue and this content worktree. Episode work happens
here. The source repository need not exist in the runtime, and the absence of `profiles/` here is normal.
Templates come from the current profile's `$HERMES_HOME/templates/`; knowledge and episode files
come from this checkout. Each profile's private memory stays in its own Hermes home.

**Already running a scripting profile:** verify the executing agent's mapped UUID owns the issue
and the runtime profile matches its role. Then perform that role's assigned work here under its
installed instructions and WORKFLOW.md. For example, Script Architect running `script-architect`
conducts the Architect interview here. Do not route its own work away or launch another Hermes session.
If identity, ownership, or profile selection conflicts, report the exact mismatch to Head Script Writer;
never guess a replacement or read another profile's private memory.

**Other agents:** route scripting work to Head Script Writer for assignment. Do not take over a role
merely because you can read its instructions. Missing prerequisites or rollout verification still block
the relevant action; a matching profile alone does not authorize bypassing WORKFLOW.md.

**Video production (not defined).** Everything after `Scripted` (filming, editing, thumbnails, titles,
publishing, and whatever else it turns out to need) is meant to be run by agents with human checkpoints. None of
it has been designed. Do not invent stages, tools, or checkpoints, and do not treat `Filmed` and `Published` as
anything more than boxes Jeremy ticks. If a request needs this workflow, say it is not defined and follow
`SKILLS.md` (`route`).

</two_workflows>

## Where work comes from and where you talk

<where_work_comes_from_and_where_you_talk>

Work is assigned as Multica issues, and episode communication happens in their history (see
`STYLE.md`). Multica owns current status and assignment; GitHub owns PR review and merge evidence;
accepted content is on git main. Follow `WORKFLOW.md` for permitted transitions and recipients.
`Interview step:` is conversation progress only. Old Pipeline boxes, Phase fields, review scores,
and Head logs never establish readiness, ownership, or completion.

If a required tool, issue field, prerequisite, or verified handoff mechanism is missing, report the
specific blocker to Head. Do not claim a transition occurred or substitute a manual profile launch.
Deployment evidence lives in `docs/validation/multica-pr-workflow.md`; instructions alone do not
prove live capability. Updating this checkout does not update an existing Multica worktree automatically.

</where_work_comes_from_and_where_you_talk>

## Session steps

<session_steps>

1. **Read the issue.** Know exactly what you were asked to do, for which episode or item, and who assigned it.
2. **Read the state** from the issue's current ownership/status, Doneness, linked PRs, and accepted
   upstream artifacts, following `WORKFLOW.md`. Say "unknown" where evidence is missing.
3. **Do your assigned role,** within `SOUL.md` and your installed profile. A matching scripting agent
   performs its own stage here. Other agents route to Head; workers never create or dispatch issues.
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

- Canonical Markdown stays in its original location, including root agent instructions.
  `python3 scripts/sync_knowledge.py` creates searchable copies of tracked and non-ignored
  Markdown throughout the repo in `docs/knowledge/repository/`, skipping hidden runtime trees.
- After cloning or editing Markdown, run the sync before discovery. It refreshes copies,
  runs `okf index docs/knowledge/`, and validates the complete bundle. `okf index` alone
  does not refresh source copies. New source Markdown needs YAML frontmatter with `type`.
- Discover context with `okf search docs/knowledge --text "<concept>"`,
  `okf show docs/knowledge <id>`, and `okf backlinks docs/knowledge <id>` before raw reads.
- Edit originals, never generated copies. Run `python3 scripts/sync_knowledge.py --check`
  to check freshness without writing. See `docs/knowledge/playbooks/repository-indexing.md`.

</code_discovery_and_knowledge_tools>
