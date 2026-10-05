# Rubric: is this a good first issue?

<!--
THIS IS THE PART YOU WRITE. The skill in SKILL.md executes whatever checks
you define here. It ships empty on purpose: the judgment is your work.

A filled rubric must contain:

1. At least one row in the checks table. Each row needs all four columns:
   - Check: a short name (used in the output JSON).
   - Evidence: exactly what to look at, and where. Name the source
     (repo-facts block, issue body, comment thread, or the locations in
     references/evidence-guide.md). "The repo" is not a source; "the last
     5 default-branch commit dates" is.
   - Pass condition: a condition someone else could apply and get your
     answer. Prefer thresholds with numbers ("a maintainer commented
     within 30 days") over adjectives ("maintainer is responsive").
   - Weight: `required` (a fail here rejects the issue) or `preferred`
     (never changes the verdict; a nice-to-have that helps rank the
     issues you accept).

2. A verdict rule below the table: how the check grades combine into
   accept or reject, including how `unclear` is treated. The verdict
   space is binary. If you write no rule for `unclear`, the skill treats
   it as fail.

Cover what actually kills first contributions. The lecture named four
families: the maintainer is alive, the repo is in use, the scope fits a
newcomer, and nobody else is already on it. A rubric that ignores a family
will fail eval issues designed around that family.
-->

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| maintainer_alive | Last 5 default-branch commits | Last 5 default branch contains atleast one update from within the last 90 days from captured date or from today in live mode. Do not include bots. | required |
| repo_active | Repo: Archived: | Passes if Archived is No | required |
| maintainer_response | Maintainer first-response sample (5 recently updated issues) | Pass if a maintainer responded to any comment in the last 5 list within 33 days. Pass if every samples issue without a maintainer comment has been opened for less than 33 days from capture date (today in live mode) | required |
| ai_contribution | Contribution Policy | Pass: If AI generated or AI assisted is allowed or AI is not mentioned, Fail: Only if AI assisted is not allowed | required |
| reproduction | Issue is Reproducible | Pass if the issue contains reproduction steps and no one has had made any comments about having issues with reproducing it. | preferred |
| scope | Issue Text | Fails if any of the following: the issue explicility refers to it's self as an umbrella or tracking issue, is a support request, issue has multiple attempts over more than 365 days, the issue is being debated and it has not be settled, a maintainer says the fix touches core internals, if it's a feature request that was not opened by one of the maintainers and no maintainer has endorsed; Otherwise pass | required | 
| issue_available | assignees and linked PRs | Fails: if someone has been assigned, if issue has open PR, comments exist of someone saying they are working on it within 90 days from capture ddate (or from today in live mode), another PR is mentioned in the comments; Otherwise Pass | required | 

## Verdict rule
<!-- State how the grades above combine into accept or reject, and how
unclear is treated. Example shape (write your own): "accept if every
required check passes; preferred checks never change the verdict, they
rank accepted issues; unclear counts as fail." -->
All of the required checks have to explicitly pass. The preferred checks can be pass or fail, but will help to provide a ranking mechanism for bulk PR evaluation. If there is any time that it is unclear or ambiguous it must fail.