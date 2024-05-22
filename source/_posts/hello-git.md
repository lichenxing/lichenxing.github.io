---
title: hello-git
date: 2024-05-22 14:04:52
tags: git
---
最近在搭博客过程中经常用到git，把之前学习git的内容再复习一下

Git是一种开源的分布式版本控制系统，主要用于跟踪和管理源代码的更改。它由Linus Torvalds在2005年开发，最初是为了支持Linux内核开发。Git的设计目标是高效处理大规模项目，同时能够保持速度和数据完整性。以下是对Git的一些关键特性的介绍：

# 1. 分布式版本控制
Git与集中式版本控制系统（如SVN、CVS）不同，它是分布式的。这意味着每个开发者的工作目录都是一个完整的代码仓库，包括所有的历史版本记录。这种设计使得Git具有以下优势：
- **离线工作能力**：开发者可以在本地进行提交、创建分支等操作，即使没有网络连接。
- **备份和恢复**：由于每个克隆的仓库都包含完整的历史记录，数据的冗余性提高了可靠性。

# 2. 强大的分支模型
Git的分支（branch）管理非常轻量且灵活，允许开发者快速创建、合并和删除分支。常见的分支策略包括：
- **功能分支（Feature Branch）**：每个新功能都在一个独立的分支上开发，完成后再合并到主分支。
- **修复分支（Hotfix Branch）**：用于紧急修复生产环境中的问题。
- **发布分支（Release Branch）**：在发布新版本前进行的最后调试和修复工作。

# 3. 高效的合并和冲突解决
Git使用三方合并（Three-way Merge）算法，可以高效地合并不同分支的代码变更。即使在多人协作中出现冲突，Git也提供了丰富的工具来帮助解决冲突，例如：
- **命令行工具**：如`git merge`和`git rebase`。
- **图形化工具**：如GitKraken、Sourcetree等。

# 4. 提交和历史记录
每次提交（commit）都包含一组文件的快照及其元数据，如作者、时间戳和提交信息。提交记录可以通过哈希值唯一标识。常用的历史记录命令包括：
- `git log`：查看提交历史。
- `git diff`：比较文件差异。
- `git blame`：查看每行代码的最后修改记录。

# 5. 分布式协作
Git支持多种协作方式，如通过GitHub、GitLab等平台进行代码托管和协作。开发者可以通过克隆（clone）、拉取（pull）和推送（push）来同步代码变化。此外，Pull Request（合并请求）和Code Review（代码审查）功能进一步增强了协作的效率和代码质量。

## 基本命令
以下是一些常用的Git命令及其简要说明：
- `git init`：初始化一个新的Git仓库。
- `git clone [url]`：克隆一个远程仓库到本地。
- `git add [file]`：将文件的更改添加到暂存区。
- `git commit -m "message"`：提交暂存区的内容。
- `git status`：查看当前工作目录的状态。
- `git push`：将本地提交推送到远程仓库。
- `git pull`：从远程仓库拉取并合并更新。
- `git branch`：列出、创建或删除分支。
- `git checkout [branch]`：切换到指定分支。

----
## Git实践

- **创建了本地版本仓库并将文件提交到本地仓库 常用操作**：
1、mkdir 创建一个文件夹
2、cd 进入该目录
3、pwd 显示该目录路径
4、git init 将创建的文件夹 变成一个本地仓库
5、git add 文件名
6、git commit -m "这里通常对提交的文件做一个简单的说明"
7、git status 随时掌握工作去的状态
8、git diff 查看修改内容
9、git log 查看历史记录
10、git log  --pretty=oneline  查看历史记录（带过滤）
11、git reflog 用来记录每一次的命令
12、git reset --hard commit_id 返回到历史版本
13、cat 文件名  查看文件内容
14、git checkout -- 文件名  实质是用版本库里面的文件版本替换工作去的版本
15、git rm 文件名  删除文件  直接用rm命令或者在工作区中删除会造成版本库和工作区中文件不一致

- **远程托管**：
16、git remote add origin ssh地址（ssh地址为github上创建的仓库时生成的）
17、git push -u origin master 第一次把当前分支master的所有内容推送到远程  
18、git push origin master 非首次推送
19、git clone ssh地址  从远程库克隆     git remote -v 查看远程库信息
     
- **分支管理**：
20、git branch 查看分支
21、git branch branch_name 创建分支( branch_name为自定义的分支名称）  
22、git checkout branch_name 切换分支
23、git checkout -b branch_name  创建并切换分支
24、git merge branch_name 合并某分支到当前分支
25、git branch -d branch_name 删除分支
26、git log --graph 查看分支合并图
27、git merge --no-ff branch_name  普通模式下的合并，合并后的历史有分支，能看出来曾经做过合并
28、git stash 把当前工作现场“隐藏”
29、git stash list 查看隐藏的工作现场
30、git stash apply 恢复工作现场，但是恢复后，stash内容并不删除，需要git stash drop 删除
31、git stash pop 恢复工作现场的同时，stash内容也被删除
32、git branch -D branch_name 强行丢弃一个没有被合并过的分支

- **创建标签**：
33、git tag tag_name 创建一个标签，默认为HEAD，也可以指定一个commit id
34、git tag -a tag_name  -m "此处指定标签信息"
35、git tag -s tag_name  -m "此处用PGP签名标签"
36、git tag 查看所有标签
37、git show tag_name 查看标签信息

- **操作标签**：
38、git tag -d tag_name 删除一个本地标签
39、git push origin tag_name 推送某个标签到本地
40、git push origin --tags 推送全部未推送过的本地标签
41、git push origin ： refs/tags/tag_name 删除一个远程标签

- **自定义git**：
42、git config  --global color.ui true
43、git config  --global alias.st status 设置status的别名为st
44、git config  --global alias.last 'log -1' 配置了一个git last，显示最后一次提交信息

注意：当git无法自动合并分支时，就必须首先解决冲突。解决冲突后，再提交，合并完成
注意： 要add的文件必须放在创建的文件夹目录或子目录（即就是工作区，.git文件就是版本区）