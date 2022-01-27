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

  git log --graph --all --oneline --decorate
```