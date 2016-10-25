# Git

## Sort remote branches by last commit

```
git for-each-ref --sort='-authordate:iso8601' --format='%(authordate:iso8601) %(authorname)%09%(refname)' refs/remotes
```
