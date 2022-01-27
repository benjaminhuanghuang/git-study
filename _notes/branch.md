  ## Compare branches
```
  git diff --color-words master..new_feature

  git diff --color-words master..new_feature^^
```

Only list branches whose tips are reachable from the specified commit
```
  git branch --merge
```

## Rename(move) branch
```
  git branch -m XXXX   
```

## reset
- soft
  moves HEAD
  does not change staging index
  does not chagne working directory
```
  git reset --soft 
```
- mixed
  moves HEAD
  Change staging index to match repository
  does not chagne working directory
```
  git reset --mixed
```

- hard
  moves HEAD
  Change staging index to match repository
  Chagne working directory to match repository
```
   git reset --hard
```