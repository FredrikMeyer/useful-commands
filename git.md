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

## Undo last commit

```
git reset HEAD~
```

(only if you haven't already pushed)
