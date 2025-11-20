---
icon: code-branch
---

# Git

## Comparing branches and files

```sh
git diff main..new-feature
```

Shows the diff between the `main` and the `feature` branches.

```sh
git diff main..new-feature -- README.md
```

Shows the diff between the branches just for the `README.md` file.

## Working with branches

```sh
git branch –n old_name new_name
```

Renames a branch.

## Stashes

How to check stash content:

```sh
git stash show
```

Exact diff of the stash:

```sh
git stash show -p
```
