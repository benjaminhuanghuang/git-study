Upstream 分支是远程仓库上由本地仓库中的本地远程分支跟踪的分支

当我们在 Git 中创建一个分支时，我们必须设置一个 Upstream 分支才能正常工作。
```
# Create branch feature1
$ git checkout -b feature1


# 使用带有 -vv 选项的 git branch 命令检查跟踪分支。
$ git branch -vv
* feature1  741a786 Initial commit
main  741a786 [origin/main] Initial commit

可以看到 main 分支有一个跟踪分支和一个与之关联的 Upstream 分支。相比之下，我们刚刚创建的分支 feature1 没有跟踪分支，也没有与之关联的 Upstream 分支。
```


使用带有 --set-upstream 选项的 git push 命令设置 Upstream 分支
```
$ git push --set-upstream origin feature1
```
