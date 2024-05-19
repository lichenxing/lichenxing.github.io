---
title: SSH Key
date: 2024-05-19 12:25:30
tags: 
  - github
  - ssh
---
# 问题现象：

```
hexo d
INFO  Validating config
INFO  Deploying: git
INFO  Clearing .deploy_git folder...
INFO  Copying files from public folder...
INFO  Copying files from extend dirs...
[master ddf123e] Site updated: 2024-05-18 18:16:33
 2 files changed, 2 insertions(+), 2 deletions(-)
/Users/oo/.ssh/config line 14: keyword hostname extra arguments at end of line
/Users/oo/.ssh/config line 17: keyword identityfile extra arguments at end of line
/Users/oo/.ssh/config: terminating, 2 bad configuration options
致命错误：无法读取远程仓库。

请确认您有正确的访问权限并且仓库存在。
FATAL Something's wrong. Maybe you can find the solution here: https://hexo.io/docs/troubleshooting.html
Error: Spawn failed
    at ChildProcess.<anonymous> (/Users/oo/myblogs/blog/node_modules/hexo-deployer-git/node_modules/hexo-util/lib/spawn.js:51:21)
    at ChildProcess.emit (node:events:520:28)
    at ChildProcess._handle.onexit (node:internal/child_process:294:12)
```

# 问题分析：

根据问题现象进行分析，Git上传代码时鉴权失败，SSH 配置文件参数报错，SSH 配置文件解析失败，从而无法进行 Git 部署。

# 解决办法：

检查配置文件，重新生成SSH Key。



---



在 Mac 上为 GitHub 设置 SSH Key 需要按照以下步骤操作：

### 1. 检查现有的 SSH Key

首先，检查你的 Mac 是否已经有 SSH Key。打开终端（Terminal），输入以下命令：

```sh
ls -al ~/.ssh
```

这将列出 `~/.ssh` 目录下的文件。如果你看到 `id_rsa` 和 `id_rsa.pub` 文件，这表示你已经有 SSH Key，可以跳过生成新 Key 的步骤。

### 2. 生成新的 SSH Key

如果你没有现有的 SSH Key，或者想生成一个新的，可以使用以下命令：

```sh
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

替换 `your_email@example.com` 为你在 GitHub 上使用的电子邮件地址。然后，系统会提示你指定保存位置和文件名。默认情况下，它会保存在 `~/.ssh/id_rsa`。

接着，它会提示你输入一个 passphrase（密码短语）。你可以选择设置一个安全的密码短语，也可以直接按 Enter 跳过。

### 3. 启动 SSH 代理

确保 SSH 代理正在运行，并将你的 SSH Key 添加到 SSH 代理中。输入以下命令：

```sh
eval "$(ssh-agent -s)"
```

这将启动 SSH 代理。然后，添加你的 SSH Key 到代理中：

```sh
ssh-add ~/.ssh/id_rsa
```

### 4. 添加 SSH Key 到 GitHub

现在你需要将公钥添加到你的 GitHub 账户中。首先，复制你的 SSH 公钥：

```sh
pbcopy < ~/.ssh/id_rsa.pub
```

这会将公钥复制到剪贴板。

接着，打开 GitHub，登录到你的账户，按照以下步骤操作：

1. 点击右上角的个人头像，然后选择 “Settings”。
2. 在左侧菜单中，选择 “SSH and GPG keys”。
3. 点击 “New SSH key” 按钮。
4. 在 “Title” 字段中输入一个描述性名称（例如 “My MacBook”）。
5. 在 “Key” 字段中粘贴你复制的公钥。
6. 点击 “Add SSH key” 按钮。

### 5. 测试连接

最后，测试是否正确配置了 SSH Key，使用以下命令：

```sh
ssh -T git@github.com
```

如果一切配置正确，你会看到一条欢迎信息，类似：

```
Hi username! You've successfully authenticated, but GitHub does not provide shell access.
```

这表示你已经成功通过 SSH 连接到 GitHub。

### 总结

以上步骤涵盖了在 Mac 上为 GitHub 设置 SSH Key 的过程。从生成 SSH Key，到配置 SSH 代理，最后添加到 GitHub 账户并测试连接。按照这些步骤操作，你应该能够顺利配置并使用 SSH Key 来进行 Git 操作。
