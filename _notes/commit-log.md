## Filter log
```
git log -3

```

fiter by date
```
  git tlog --since=2000-01-01

  git tlog --until=2000-01-01

  git tlog --until="3 days ago"

  git tlog --after=2.weeks --before=3.days
```

filter by author
```
  git log --author="Kevin"
```

regex
```
  git log --grep="Initail"
```

all logs after one commit 
```
  git log xxxxxxx..HEAD
```

```
  git log filename.html
```
## Format commit log
```
  git log -p

  git log --stat

  git log --format=short

  git log --format=oneline

  git log --oneline

  # really useful before rebase a branch
  git log --graph --all --oneline --decorate        
```

return commit where topic brach diverges
```
  git merge-base master new_feature
```