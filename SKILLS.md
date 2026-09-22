# SKILLS: BurgoyneBlue

<project_source project="delongpa" file="SKILLS" format="hybrid-xml-markdown" />

Project-level skills for any agent in this project. All follow `SOUL.md`. Role-specific skills (interviewing,
scoring, coordinating) live in each profile's own `SKILLS.md`, and the process is in `WORKFLOW.md`. Do not
restate either.

---

## Skill: orient

<skill_orient>

**Purpose.** Find out where things stand at the start of a session, from evidence.

### Steps

1. Read the issue you were given, and its comments.
2. If it names an episode, read that episode's entry and `Pipeline:` line in `series/SERIES.md`, and the
   `Phase:` line of each stage output that exists:

```bash
EP=series/episodes/<folder>
grep -n "^- Pipeline:" series/SERIES.md
grep -n "^Phase:" $EP/0*.md
ls series/head-pending 2>/dev/null
```

3. Say what is known and what is unknown. A missing file or entry means "unknown", not "not started".

### Rules

- Report states only. Never judge whether a stage is good or ready (the Reviewer's log and the Pipeline box are
  the only evidence).

</skill_orient>

## Skill: route

<skill_route>

**Purpose.** Decide where a request belongs, and send it there instead of doing it.

### Steps

| Request | Goes to |
|---|---|
| Start, advance, or check on an episode; a held stage; parking | The Head Scriptwriter (`script-head`) |
| Content for a stage: ideas, structure, drafting, polish | That stage's profile, started with `script-<stage> chat --in <this folder>` |
| Scoring a stage | The Reviewer, asynchronously, per `WORKFLOW.md` |
| Anything after `Scripted` (video production) | Not defined. Say so, and ask Jeremy whether he wants to design that workflow first |
| Changing the process | `propose-process-change` |

If a request fits none of these, ask Jeremy one question about what he wants (`STYLE.md`).

### Rules

- Never do a stage profile's work yourself, even if it looks quick.

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
3. Ask Jeremy whether to apply it (`raise-a-decision`). Do not edit anything until he says yes.
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
3. If a `docs/knowledge/` bundle exists, use `okf search` / `okf show` / `okf backlinks` for
   concept context.
4. Fall back to grep/find or reading files only for what the indexes do not cover.

### Rules

- A missing index directory means skip that tool and say nothing of it; never install or index
  one yourself (`SOUL.md`, rule 2).
- Report what the tool showed as evidence, per `STYLE.md` (Citing tool evidence).

</skill_tool_lookup>
