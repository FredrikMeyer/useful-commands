# Git-kommandoer

## amend

Legge til mer på siste commit (*før* den er pushet).

```
git commit --amend --no-edit
```
eller
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
