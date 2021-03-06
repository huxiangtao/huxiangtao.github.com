---
layout: post
title: "github director"
category : git 使用指南
articleType : blog
---

github Inc 作为远程代码仓库，它有自己的一套版本管理系统，拥有和svn类似的分支管理。
而本地仓库与远程仓库是相对应的，在远程开了新的分支后，本地最好也同步一下——开一个同名分支，这样的话，让远程仓库的代码与本地代码高度统一。
以便于管理，在各个测试分支上做新的开发，最后将完好的代码merge到Master分支上，再将本地的master分支代码push至远程仓库，以保证远程仓库代码的稳定与完整。

应该说，git与传统的svn版本管理系统最大的区别就是分布式，在本地能够拥有全套的代码，并且和远程仓库中的是一模一样。当然，这只是自己的想法，大家完全可以再本地开无数
个不稳定分支，做各种开发，最后讲稳定的版本以阶梯的形式，一点一点合到master上，而在远程，只需保存一个master分支就行了。

如果是一个小团队协同开发，这就非常实用。远程只保存稳定版本的主干上的代码，分支的话，在本地各个程序员都不同，不同的分支数量，不同的分支内容，不同的风格等等。
最后，本地可以合成代码到一个预发布的分支上，这个分支由一个比较权威的管理员来管理，我认为可以在远程开一个相同的分支，以便于保存预发布的代码，主干的管理员可以根据情况
将这个分支合到master上，然后，最后的Push则由这位仁兄来完成了。

昨日提交代码发现，git merge合并功能，在不同的分支上想将别的分支的代码合并到该分支的时候，往往是合并了其他分支的commit（提交），因此，commit -m"" 里的提交描述是继承自
前一次的提交，不管这个提交的代码是提在哪个分支上，后面将这个分支的代码合并到另外一个分支的时候，在github上会相应的出现之前在原来分支提交代码时候的message。
例如：
我在gh-pages分支上开发、提交、push。完了之后，甩出base master分支一大截，我想将gh-pages分支上的稳定代码合并到master上，只要切换到master分支上，然后git merge gh-pages,这样gh-pages
分支上的代码就合并到master上了，此时，其实可以直接push了，push之后，我们会发现，在github上的master分支上，message继承了gh-pages分支上的提交。

未完待续......


