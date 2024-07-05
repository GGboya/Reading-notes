让本地的git log保持线性提交的历史

基于main分支，创建一个新的分支dev，然后main分支和dev分支都进行了开发。此时他们的commit历史应该是分叉的，因为在不同的分支进行了不同的开发工作。

在Git中，如果想让本地的git log保持线性提交的历史，可以通过以下步骤来实现：
在dev 分支，进行git rebase main，修改完冲突之后,切换回main分支，进行git merge dev。这样子git log就是线性的了