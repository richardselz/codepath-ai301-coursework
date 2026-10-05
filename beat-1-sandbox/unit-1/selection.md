# Unit 1 — Issue Selection

Path: `beat-1-sandbox/unit-1/selection.md`

Record of the issue carried into Unit 2, and of the evaluation runs that produced
`eval-run.txt`. This file is graded at the path above; a copy kept anywhere else in
the repository is not read.

Complete every labelled field below. Each is graded on its own; content placed under the
wrong label is not graded.

---

## Selected issue

**Issue link**

https://github.com/codepath/pathreview-ai301-fa26-s3/issues/51

**Verdict output**

[Your skill's live-mode output for this issue, pasted verbatim and ending with the
fenced JSON verdict block. A summary does not satisfy this field.]

**The verdict must record `accept` for this issue.** Choose an issue your own skill
accepts. If your skill rejects every candidate you try, that is a signal about your
rubric rather than about the issues: revise it and re-run — retries are unlimited and a
partial re-run costs about $0.20 — or run the skill on different candidates. Output
recording `reject` for the issue you chose earns no credit for this field.

```
I graded all three against your rubric. Only #51 is accepted. #68 and #54 are rejected because classmates already have open PRs linked to them.

  Accepted
  1. #51: Add a migration validation step to CI (enhancement, tier-3). Your fit profile in scope.md is still the placeholder text, so I couldn't rank by fit. It wins because it's the only one accepted.
     - Every required check passes. Nobody is assigned and no PRs are linked. One classmate, Gabbykoms, posted claim comments, but your house rule says those don't block you.
     - Preferred check failed: reproduction. There are no repro steps, since it's a feature request rather than a bug.
     - Watch out: Gabbykoms points out that main already has a mismatch between the migrations and the models (uq_users_email). That means a correct CI check would fail on day one. They asked how to handle this
       and no maintainer has answered. I graded scope as pass because it's an unanswered question, not a debate. But your rule says "ambiguous must fail," so you could argue it the other way. If that question
       matters to you, tighten the scope wording in the rubric. Expect 5–7 hours of work, not a quick fix.

  Rejected
  - #68: Empty-index ZeroDivisionError. Failed issue_available: three open PRs are linked (#74, #83, #89). The 36 claim comments don't count against it under your house rule, but your rubric fails any issue with
    an open PR, and the house rule doesn't override that.
  - #54: Resume section detection with leading whitespace. Failed issue_available: open PR #76 is linked.

  Two things you might want to change in the rubric:
  - The house rule says shared issues "cost nobody anything," but your open-PR condition still rejects #68 and #54. If you want to allow working on issues that already have classmates' PRs, change
    issue_available.
  - For the maintainer_response sample, no maintainer has commented on any of the five issues. They pass only because every one was opened less than 33 days ago. This repo has no evidence of maintainer replies at
    all.

  [
    {
      "item": "https://github.com/codepath/pathreview-ai301-fa26-s3/issues/51",
      "checks": [
        {"name": "maintainer_alive", "grade": "pass", "evidence": "Newest default-branch commit 2026-09-16 by Aburke225 (human), 18 days before today"},
        {"name": "repo_active", "grade": "pass", "evidence": "gh repo view: isArchived=false"},
        {"name": "maintainer_response", "grade": "pass", "evidence": "Sample #72,#59,#73,#57,#54 have no maintainer comments, but all were opened 2026-09-10..09-16 (<33 days before 2026-10-04)"},
        {"name": "ai_contribution", "grade": "pass", "evidence": "docs/CONTRIBUTING.md and PR template don't mention AI; no AI_POLICY.md/AGENTS.md"},
        {"name": "reproduction", "grade": "fail", "evidence": "Enhancement body has no reproduction steps"},
        {"name": "scope", "grade": "pass", "evidence": "Bounded CI task opened by maintainer Aburke225 (COLLABORATOR); not umbrella/support; no attempts; contributor's drift question unanswered but not a 
  debate"},
        {"name": "issue_available", "grade": "pass", "evidence": "assignees=[], no linked or cross-referenced PRs; Gabbykoms's 2026-09-30 claim ignored per house rule"}
      ],
      "verdict": "accept"
    },
    {
      "item": "https://github.com/codepath/pathreview-ai301-fa26-s3/issues/68",
      "checks": [
        {"name": "maintainer_alive", "grade": "pass", "evidence": "Newest default-branch commit 2026-09-16 by Aburke225 (human), 18 days before today"},
        {"name": "repo_active", "grade": "pass", "evidence": "gh repo view: isArchived=false"},
        {"name": "maintainer_response", "grade": "pass", "evidence": "Sample issues unanswered by maintainers but all opened <33 days ago"},
        {"name": "ai_contribution", "grade": "pass", "evidence": "docs/CONTRIBUTING.md and PR template don't mention AI"},
        {"name": "reproduction", "grade": "fail", "evidence": "Body describes the bug and names a covering xfail test but gives no reproduction steps (many commenters reproduced it without trouble)"},
        {"name": "scope", "grade": "pass", "evidence": "Single-function bug, maintainer-opened, labeled good first issue, est. 2-4 hours"},
        {"name": "issue_available", "grade": "fail", "evidence": "Open PRs #74, #83, #89 cross-reference this issue"}
      ],
      "verdict": "reject"
    },
    {
      "item": "https://github.com/codepath/pathreview-ai301-fa26-s3/issues/54",
      "checks": [
        {"name": "maintainer_alive", "grade": "pass", "evidence": "Newest default-branch commit 2026-09-16 by Aburke225 (human), 18 days before today"},
        {"name": "repo_active", "grade": "pass", "evidence": "gh repo view: isArchived=false"},
        {"name": "maintainer_response", "grade": "pass", "evidence": "Sample issues unanswered by maintainers but all opened <33 days ago"},
        {"name": "ai_contribution", "grade": "pass", "evidence": "docs/CONTRIBUTING.md and PR template don't mention AI"},
        {"name": "reproduction", "grade": "pass", "evidence": "Body has 'Steps to reproduce' snippet; commenters all reproduced it successfully"},
        {"name": "scope", "grade": "pass", "evidence": "Bounded regex fix in _detect_sections(), maintainer-opened, labeled good first issue"},
        {"name": "issue_available", "grade": "fail", "evidence": "Open PR #76 cross-references this issue"}
      ],
      "verdict": "reject"
    }
  ]
```

---

## Eval iterations

**Run history**

1. Smoke test (`--limit 3`, partial): `agreement: 2/3 scored items`
   — issue-01 missed: maintainer_response failed.
2. Full run 1 (`eval-run-1.txt`): `agreement: 13/20 scored items  (bar: 18/20: below the bar)`
   — 7 misses; clear-accept 2/8. maintainer_response rejected 4 gold-accepts (01, 09, 14, 16).
3. Partial (--only 8 issues): agreement: 6/8 — loosened maintainer_response to 33 days; fixed 01, 16; 14 still fails (no repo-creation field in bundle)
4. Partial (-- only 8 issues): agreement: 5/8 - caused regression on issue-01
5. Partial (--only 01,14,16): agreement: 3/3 — added "recent sampled issues don't count" clause
6. Partial (--only 03,08,09): agreement: 3/3 — 90-day claim limit, open PRs only
7. Partial (--only 04,19,20): 1/3 - Rejects a feature
8. Partial (--only 04,09,19,20): 4/4 — umbrella must be explicit; feature requests need maintainer buy-in
9. Full run 2 (eval-run-2.txt): agreement: 20/20 scored items (bar: 18/20: PASS)

**Issue analysis**
|Issue|Gold|Verdict|Agree|Note|
|-|-|-|-|-|
|issue-19|accept|accept|yes|| 

In the first few runs, issue-19 was failing due to an issue with how I had stated "umbrella/tracking issue" and once I consulted with Claude we were able refine it by making sure that the issue only is rejected if it `explicitly` states that it's an umbrella or tracking issue. Issue bundles several independent work items (matcher complexity, UI threading, multiprocessing, lazy matching, threaded rewrite application), so it is a multi-part tracking issue and not a bounded newcomer task

**Check rationale**

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| maintainer_response | Maintainer first-response sample (5 recently updated issues) | Pass if a maintainer responded to any comment in the last 5 list within 33 days. Pass if every samples issue without a maintainer comment has been opened for less than 33 days from capture date (today in live mode) | required |

The maintainer_response requires that a maintainer can comment within a little over one month period which was the reason for giving it a value of 33 days. It also explicitly passes if the issue has been open for less than 33 days and no maintainer response. 

**Trade-offs**

A repo will still pass if all issues are recent within 33 days, but "no maintainer has commented on any of the five issues."

---

## Selection rationale

Graded on whether all three are answered, in your own words. Not on how good the
reasoning is, and not on length — a short honest answer to each earns the full marks.
This is also the basis for the claim comment you write in Unit 2.

**Selection rationale**

Answer all three:
1. The issue's fit to your interests and to the time available.
   - I have had experience with migration scripts before and I believe that this issue is obtainable with the help of Claude.
2. What the verdict identified correctly, and what you weighed that the rubric could
   not.
   - The automated script rejected 54 and 68 due to open PRs although 68 would have been my original choice.
3. The anticipated difficulty in claiming it.
   - Multiple other students have already claimed the issue and are actively working on it. 

---

Related paths: `eval-run.txt` in this directory; your skill's files in
`tools/issue-select/`.
