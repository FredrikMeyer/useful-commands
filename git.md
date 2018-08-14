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
