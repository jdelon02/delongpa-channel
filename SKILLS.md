# SKILLS: BurgoyneBlue

Project-level skills for any agent in this project. All follow `SOUL.md`. Role-specific skills (interviewing,
scoring, coordinating) live in each profile's own `SKILLS.md`, and the process is in `WORKFLOW.md`. Do not
restate either.

---

## Skill: orient

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

---

## Skill: route

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

---

## Skill: raise-a-decision

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

---

## Skill: propose-process-change

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

---

## Video pipeline (not yet defined)

Placeholder. This section is empty on purpose.

When Jeremy designs the video workflow, its stages, the agent for each, the human checkpoints, and the files each
stage reads and writes go here or in a `WORKFLOW`-style file he chooses. Until then, no agent acts on this. Known
so far, from Jeremy:

- The whole workflow will be agentic, because he has no video experience.
- It will have defined places for human intervention, which have not been designed.
- Publishing is always his call (`SOUL.md`, rule 1).
