1. Lists the 20 files changed most often in the last 12 months (by commit count). --name-only outputs only filenames; the pipeline counts and sorts them descending.
```
git log --format=format: --name-only --since="1 year ago" | sort | uniq -c | sort -nr | head -20
```
2. Shows every author + their commit count, sorted by most commits first. --no-merges excludes merge commits.
```
2. git shortlog -sn --no-merges
```
```
```
```
