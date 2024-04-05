# Useful git commands

### Comparing branches and files

```
git diff main..new-feature
```

Shows the diff between the `main` and the `feature` branches.

```
git diff main..new-feature -- README.md
```

Shows the diff between the branches just for the `README.md` file.

### Working with branches

```
git branch –n old_name new_name
```

Renames a branch.

### Stashes

How to check stash content:

```
git stash show
```

Exact diff of the stash:

```
git stash show -p
```
