# Git-kommandoer

## amend

Add more on last commit (*before* push)

```
git commit --amend --no-edit
```
or
```
git commit --amend -m "New commit message"
```

## Remove untracked files

```
git clean -fd
```

*Deletes* all untracked files from the working directory.

## Revert a single file to last commit

```
git checkout filename
```

## Undo add file to commit

```
git reset filename
```

## Undo last commit

To keep the file changes:

```
git reset HEAD~
```

Also restore file changes (ref [stackoverflow](https://stackoverflow.com/questions/927358/how-to-undo-the-most-recent-commits-in-git)):

```
git reset --hard HEAD~
```

(only if you haven't already pushed)

## Inspect stash

```
git stash show stash@{0} -p
```

Shows the diff of `stash@{0}`.

## Move commits from branch to branch

```
git branch newbranch      # Create a new branch, containing all current commits
git reset --keep HEAD~3   # Move master back by 3 commits (Make sure you know how many commits you need to go back)
git checkout newbranch    # Go to the new branch that still has the desired commits
# Warning: after this it's not safe to do a rebase in newbranch without extra care.
```

From [this](https://stackoverflow.com/questions/1628563/move-the-most-recent-commits-to-a-new-branch-with-git) answer on StackOverflow.

## Diff specific file or directory

```
git diff 27fa75e ada9b57 myfile.txt
```
