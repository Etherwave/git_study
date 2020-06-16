# git创建分支

第一种方法
创建分支并转到该分支
```
git checkout -b iss53
```

第二种方法
先创建分支，然后转到该分支
```
git branch iss53
git checkout iss53
```

在git commit完成该分支后

在远程增加该分支
```
git push --set-upstream origin iss53
```


