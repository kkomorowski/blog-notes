---
icon: code-branch
---

# Git

### Comparing branches and files

```shellscript
git diff main..new-feature
```

Shows the diff between the `main` and the `feature` branches.

```shellscript
git diff main..new-feature -- README.md
```

Shows the diff between the branches just for the `README.md` file.

### Working with branches

```shellscript
git branch –n old_name new_name
```

Renames a branch.

### Stashes

How to check stash content:

```shellscript
git stash show
```

Exact diff of the stash:

```shellscript
git stash show -p
```
