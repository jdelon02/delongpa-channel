---
type: "validation"
title: "Corrected handoff pilot: full Reviewer review/merge/return workflow"
description: "Validation source for scriptwriting: docs/validation/PERS-20-handoff-pilot.md."
tags: ["scriptwriting", "docs"]
source_path: "docs/validation/PERS-20-handoff-pilot.md"
---

# Corrected handoff pilot: full Reviewer review/merge/return workflow

## Purpose

This document is the non-creative validation artifact for PERS-20, the corrected follow-up to the
PERS-19 capability pilot. It records the bounded scope, PERS-19 audit findings, expected boundary
evidence, and the post-merge execution checklist. It does not declare any capability passed before
the evidence is recorded in Multica.

## Bounded scope

This pilot exercises exactly one cycle of the deployed WORKFLOW.md `multica-pr-v1` contract:

1. A non-creative validation document is committed on the exact issue-ID branch (PERS-20) from fresh
   `origin/main`.
2. A PR is created from that branch into `main` with title `PERS-20: Corrected handoff pilot`.
3. The PR is natively linked to PERS-20 via the branch-name convention.
4. Head assigns Reviewer with a combined In Review / Reviewer `--no-start` update, posts one actual
   `@The Reviewer` mention requesting the full normal review/merge/return workflow, and verifies
   the recipient run.
5. Reviewer inspects the PR at its submitted head SHA, posts a SHA-bound agent verdict comment
   (approved or changes-requested) on GitHub, records the comment reference and run in issue history,
   and if approved merges that exact revision under the expected-head guard.
6. Reviewer sets Done + Head assignment via combined `--no-start`, posts an actual
   `@Head Script Writer` mention on the PERS-14 parent, and Head verifies the receiving run.
7. Head reconciles the verdict, merge, artifact-on-main, and return receipt, then posts the result
   on PERS-14.
8. A bounded safe-repeat reconciliation verifies no duplicate dispatch.

No creative episode files are modified. No production issues are dispatched. No runbook scenarios
beyond the exercised ones are claimed passed.

## PERS-19 audit findings

PERS-19 (ID: `01a0e80e-d0ff-7154-b61b-34d69ecb8b97`, status: Done) recorded a partial-failed
contract in its metadata (`capability_pilot_result: partial-failed-contract`):

### What passed

| Capability | Evidence |
|---|---|
| Native PR association | `multica issue pull-requests PERS-19` returned PR #8; branch `PERS-19` matched issue identifier |
| Revision-specific inspection | Reviewer run `01a0e814-6d1e-764d-b942-9d9695d9eb0b` verified at head SHA `796d152` |
| Artifact on main | `docs/validation/pilot-capability-test.md` present on current main after merge commit `a0e4c81` |

### What failed / was not established

| Boundary | Finding |
|---|---|
| GitHub agent verdict comment | Reviewer posted only an issue-thread verdict; no SHA-bound agent verdict comment appeared on GitHub PR #8 |
| Guarded Reviewer merge | Head merged without the expected-head guard; no Reviewer-owned merge action |
| Reviewer return run | No Reviewer-to-Head mention on the parent issue; no correlated receiving Head run |
| Safe-repeat reconciliation | Not tested; no repeat dispatch was performed |
| Combined Done + Head update | Head separately set Done and assigned itself; the combined `--no-start` transition was not used |

### What this follow-up exercises

This PERS-20 pilot corrects every failed boundary above by requiring:

- A SHA-bound agent verdict comment on GitHub (not just an issue-thread comment)
- Reviewer-owned merge under the expected-head guard (not Head merging on Reviewer's behalf)
- Combined Done + Head `--no-start` transition with an actual `@Head Script Writer` mention
- A correlated receiving Head run that independently reconciles the verdict and merge
- A bounded safe-repeat that verifies no duplicate dispatch

## Expected boundary evidence

Each boundary below must have actual recorded evidence before this pilot is claimed complete.
Post-merge outcomes are recorded in Multica, not fabricated here.

| Boundary | Expected evidence |
|---|---|
| Native PR link | `multica issue pull-requests PERS-20 --output json` returns the actual PR URL |
| Reviewer run | `multica issue runs PERS-20 --output json` shows a run with Reviewer agent UUID `89254adf-5859-46e5-b331-8aaa18d3ed36` |
| GitHub agent verdict | A PR comment under `jdelon02` with `Agent verdict: approved` or `Agent verdict: changes-requested`, including issue ID, Reviewer UUID, run ID, inspected head SHA |
| PR merge state | `gh pr view <N>` shows `MERGED`; merge commit is an ancestor of current `main` |
| Artifact on main | `git show origin/main:docs/validation/PERS-20-handoff-pilot.md` returns this document's content |
| Reviewer return | A `@Head Script Writer` mention comment on PERS-14 from the Reviewer run, linking the finding comment and Reviewer run ID |
| Head reconciliation | A Head run correlated with the return mention, verifying the same verdict/merge/receipt |
| Safe repeat | A subsequent reconciliation that reads existing evidence and produces no duplicate review, merge, or successor dispatch |

## User decision: PERS-15 native PR exception

Recorded 2026-09-28: the user stated **"Allow a one-time PERS-15 exception"** to the absent native
PR association for historical PERS-15. This is conditional on the corrected PERS-20 pilot passing.
PERS-15's acceptance audit and PR #3 merge evidence remain required and are already verified.
This exception applies only to historical PERS-15, never to new submissions. The absent native link
is not described as repaired.

## Deployment context

- Deployment revision: `1d983afe0e00bd1d5350`
- Source PR #6: merged (deployment verification)
- Channel PR #9: merged at `44ce2ffd` (require verified pilot completion)
- PERS-19: Done, PR #8 merged at `a0e4c81`, partial-failed contract preserved
- PERS-16: blocked, assigned to Architect (`9f97901a-ad33-4333-abb6-5f683dd096c0`), recovery commit `849c1e0` preserved
- PERS-15: done, acceptance audit verified, one-time native-link exception recorded
- PERS-17/PERS-18 (Writer/Wizard): blocked on accepted Architect artifact

## Post-merge execution checklist

After the Reviewer merges this PR and returns to Head, the receiving Head run records the
following in Multica (not in this document):

- [ ] Reviewer verdict comment URL/ID on GitHub
- [ ] Inspected head SHA and Reviewer run ID
- [ ] Merge commit SHA and merged PR state
- [ ] Artifact verified on fetched main
- [ ] Reviewer-to-Head mention comment ID on PERS-14
- [ ] Correlated receiving Head run ID
- [ ] Head reconciliation result on PERS-14
- [ ] Safe-repeat reconciliation (no duplicate dispatch)

These are post-merge execution checks. Completing them in this document without actual evidence
would be fabrication. They are recorded here as a checklist for the receiving Head run only.