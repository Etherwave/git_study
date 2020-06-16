# git config

##邮箱及用户名设置
两条命令即可

```
git config --global user.mail "*******.qq.com"
git config --global user.name "*****"
```

##Git别名
在完成有关基本Git的本章之前，只有一个小技巧可以使您的Git体验更简单，更轻松和更熟悉：别名。我们不会引用它们，也不会假定您在本书的后面使用了它们，但是您可能应该知道如何使用它们。

如果您部分输入，Git不会自动推断您的命令。如果您不想键入每个Git命令的整个文本，则可以使用轻松为每个命令设置别名git config。以下是您可能要设置的几个示例：

```
$ git config --global alias.co checkout
$ git config --global alias.br branch
$ git config --global alias.ci commit
$ git config --global alias.st status
```

举例来说，这意味着git commit您无需输入，而只需输入git ci。在继续使用Git时，您可能还会经常使用其他命令。不要犹豫，创建新的别名。

该技术在创建您认为应该存在的命令时也非常有用。例如，要解决在取消暂存文件时遇到的可用性问题，可以将自己的暂存别名添加到Git：

```
$ git config --global alias.unstage 'reset HEAD --'
```

这使得以下两个命令等效：

```
$ git unstage fileA
$ git reset HEAD -- fileA
```

这似乎更清楚了。添加last命令也很常见，如下所示：

```
$ git config --global alias.last 'log -1 HEAD'
```

这样，您可以轻松查看上一次提交：

```
$ git last
commit 66938dae3329c7aebe598c2246a8e6af90d04646
Author: Josh Goebel <dreamer3@example.com>
Date:   Tue Aug 26 19:48:51 2008 +0800

    Test for current head

    Signed-off-by: Scott Chacon <schacon@example.com>
```

如您所知，Git只是将新命令替换为其别名。但是，也许您想运行外部命令，而不是Git子命令。在这种情况下，您可以使用!字符启动命令。如果您编写自己的可与Git存储库一起使用的工具，这将非常有用。我们可以通过别名git visual来演示运行gitk：

```
$ git config --global alias.visual '!gitk'
```