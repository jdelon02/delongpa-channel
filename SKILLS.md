---
type: "project-instructions"
title: "SKILLS: BurgoyneBlue"
description: "Repository Markdown source: SKILLS.md."
tags: ["delongpa", "repository"]
source_path: "SKILLS.md"
---

# SKILLS: BurgoyneBlue

<project_source project="delongpa" file="SKILLS" format="hybrid-xml-markdown" />

Project-level skills for any agent in this project. All follow `SOUL.md`. Role-specific skills (interviewing,
PR review, coordinating) live in each installed profile's own `SKILL.md`, and the process is in `WORKFLOW.md`. Do not
restate either.

---

## Skill: orient

<skill_orient>

**Purpose.** Find out where things stand at the start of a session, from evidence.

### Steps

1. Read the injected issue and history: owner/status, Doneness, episode/stage, repository,
   `original_assignee_id`, linked PRs, and Head-provided prerequisite merge revisions.
2. Resolve your role and Hermes profile through WORKFLOW.md's Agent directory. Confirm the runtime
   identity and current issue owner before editing. Read your own profile instructions.
3. Follow WORKFLOW.md's Worker start and resume and Branch and worktree protocol. Verify accepted
   upstream artifacts against fetched main and the issue branch. Read episode files for creative
   material and `Interview step:` for interview position, never as lifecycle authority.
4. Report known state and specific missing evidence. Head reconciles mismatches and missing inputs.

### Rules

- A missing file means unknown, not not-started. A Done label alone does not prove a merged PR.
- Preserve old Pipeline, Phase, scoring, review-log, and Head-log material as historical evidence;
  never update or use it to authorize work under `multica-pr-v1`.

</skill_orient>

## Skill: route

<skill_route>

**Purpose.** Recognize your own assigned role; route only work outside that role.

### Steps

First resolve role, Multica UUID, and Hermes profile through WORKFLOW.md's Agent directory.
If you already are the matching agent and own the issue, perform the assigned work in this checkout
under your installed profile. The routing rules do not prohibit an agent from doing its own role.

| Request | Action |
|---|---|
| New episode, scheduling, revisions, blockers, or work outside your assignment | Head Script Writer coordinates through Multica |
| Content for your assigned stage, with matching agent/profile and valid prerequisites | Perform the stage here; load your own installed profile's instructions |
| Content for another role, or a request received by a general agent | Report it to Head Script Writer for assignment to the mapped stage agent |
| PR review | The Reviewer, assigned by the worker's verified submission handoff under WORKFLOW.md |
| Video production after scripting | Not defined; ask Jeremy whether to design that workflow |
| Process change | `propose-process-change`, unless Jeremy has already authorized this change |

If a request fits none of these, ask Jeremy one focused question (`STYLE.md`).

### Rules

- Never take over another role's work. Do perform your own authorized role in the assigned checkout.
- Hermes profile names select runtime context; they are not Multica assignees. Use the directory's
  exact names in explanations and UUIDs in assignment operations allowed by WORKFLOW.md.
- Do not tell Jeremy to start another profile when Multica already runs the correct one.
- Do not launch a second Hermes session or create another checkout to resolve an assignment mismatch.
  Report the mismatch to Head. Workers do not create issues or dispatch successors.

</skill_route>

## Skill: raise-a-decision

<skill_raise_a_decision>

**Purpose.** Put a choice that is Jeremy's to make in front of him, in the issue.

### Steps

1. State what the decision is and why it is his, in one or two lines.
2. List the options plainly, in a neutral order, with the consequence of each (what would change, what would
   need redoing). No preference, unless he asks for a recommendation.
3. Ask, one question. Stop and wait.
4. Record his answer in his own words, in the issue and wherever the calling skill says to.

### Rules

- If he says "you decide" about something that is his to decide, decline, restate the options, and ask again
  (`SOUL.md`, rule 4).
- Publishing, process changes, and deleting or overwriting work always come through here.

</skill_raise_a_decision>

## Skill: propose-process-change

<skill_propose_process_change>

**Purpose.** Suggest a change to `WORKFLOW.md`, a profile, or these five files, without applying it.

### Steps

1. Comment on the issue with: what you would change (file and section), why, what it would affect, and what
   would stay the same.
2. Quote the evidence that prompted it, such as a failure, a confusing rule, or a gap.
3. Ask Jeremy whether to apply it (`raise-a-decision`) only if he has not already authorized the
   specific change. Existing explicit authorization remains valid; do not ask again.
4. If he says yes, make only the change he approved, and say what you changed.

### Rules

- Never apply a process change on your own initiative, however small (`SOUL.md`, rule 2).
- A change to a scripting profile's source is made in the `scriptwriting` repo and then re-installed, not in an
  installed copy.

</skill_propose_process_change>

## Video pipeline (not yet defined)

<video_pipeline_not_yet_defined>

Placeholder. This section is empty on purpose.

When Jeremy designs the video workflow, its stages, the agent for each, the human checkpoints, and the files each
stage reads and writes go here or in a `WORKFLOW`-style file he chooses. Until then, no agent acts on this. Known
so far, from Jeremy:

- The whole workflow will be agentic, because he has no video experience.
- It will have defined places for human intervention, which have not been designed.
- Publishing is always his call (`SOUL.md`, rule 1).

</video_pipeline_not_yet_defined>

## Skill: tool-lookup

<skill_tool_lookup>

**Purpose.** Answer questions about repository state or history from indexed evidence before
manual scanning.

### Steps

1. If `.codegraph/` exists, ask CodeGraph first: `codegraph explore "<question>"` (or the
   `codegraph_explore` MCP tool).
2. If `.code-review-graph/` exists, use its MCP tools for change review and impact questions
   (`detect_changes_tool`, `get_impact_radius_tool`, `query_graph_tool`,
   `semantic_search_nodes_tool`).
3. Refresh repository-wide Markdown copies with `python3 scripts/sync_knowledge.py`
   after cloning or editing source Markdown. Use `okf search docs/knowledge`,
   `okf show docs/knowledge <id>`, and `okf backlinks docs/knowledge <id>` for concept context.
   Originals stay in place; edit those rather than `docs/knowledge/repository/` copies.
4. Fall back to grep/find or reading files only for what the indexes do not cover.

### Rules

- A missing code index directory means skip that tool and say nothing of it; never install or
  index one yourself (`SOUL.md`, rule 2). The repository-wide OKF sync above is authorized.
- Report what the tool showed as evidence, per `STYLE.md` (Citing tool evidence).

</skill_tool_lookup>
