1. Lists the 20 files changed most often in the last 12 months (by commit count). --name-only outputs only filenames; the pipeline counts and sorts them descending.

  ```bash
  git log --format=format: --name-only --since="1 year ago" | sort | uniq -c | sort -nr | head -20
  ```
2. Shows every author + their commit count, sorted by most commits first. --no-merges excludes merge commits.

  ```bash
  git shortlog -sn --no-merges
  ```
3. Lists the 20 files most frequently touched in commits whose message contains "fix", "bug", or "broken" (case-insensitive). Same counting logic as #1.

  ```bash
  git log -i -E --grep="fix|bug|broken" --name-only --format='' | sort | uniq -c | sort -nr | head -20
  ```
4. Shows commit count per month (YYYY-MM) across the entire repo history. Useful for spotting activity trends.
  ```bash
  git log --format='%ad' --date=format:'%Y-%m' | sort | uniq -c
  ```
5. Lists every commit from the last year that contains any of those four words (case-insensitive) in the message. Quick way to surface emergency/revert activity.
  ```bash
  git log --oneline --since="1 year ago" | grep -iE 'revert|hotfix|emergency|rollback'
  ```
