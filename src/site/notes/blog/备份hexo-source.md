---
{"dg-publish":true,"permalink":"/blog/hexo-source/"}
---

# 检查并配置忽略文件（至关重要）

## 在执行 Git 命令前，必须确保我们不备份垃圾文件（如生成的网页和依赖包）。

- 在博客根目录 BLOG 下，检查是否存在名为 .gitignore 的文件。
- 如果没有，请新建一个文本文件命名为 .gitignore。
- 确保文件内包含以下内容（如果没有，请复制粘贴进去）：
~~~
.DS_Store
Thumbs.db
db.json
*.log
node_modules/
public/
.deploy_git/
~~~

## 处理主题文件夹的 Git 冲突（关键）

你修改了 next 里的样式。通常 next 也是一个 Git 仓库（如果你是克隆下来的）。如果不处理，你的主仓库无法备份主题里的修改。

请在文件资源管理器中打开 next：

- 查看是否有隐藏的 .git 文件夹？
- 如果有，请直接删除这个 .git 文件夹。
解释：这样做是把主题变成你项目的一部分，而不是一个独立的子仓库，确保你的 *custom.styl* 修改能被备份。


## 执行“无损”备份命令

在 BLOG 根目录下打开终端，逐行执行以下命令。

```
# 1. 初始化/重新初始化本地仓库 (这步是安全的，不会覆盖现有文件)
git init

# 2. 创建并切换到一个全新的分支，命名为 hexo-source
# (这样绝对不会影响 gh-pages 分支，实现了物理隔离)
git checkout -b hexo-source

# 3. 添加所有源码文件到暂存区
# (因为配置了 .gitignore，它会自动忽略 public 和 node_modules)
git add .

# 4. 提交到本地仓库
git commit -m "备份博客源码和样式修改"

# 5. 重新关联远程仓库
# (先尝试删除旧关联，防止报错，这一步很安全)
git remote remove origin 2>$null
# (添加你的远程仓库地址)
git remote add origin https://github.com/ICEY4040727/HOME.git

# 6. 推送到远程的 hexo-source 分支
# (注意：我们推送到 hexo-source，而不是 gh-pages)
git push -u origin hexo-source
```

# 可能遇到的情况及应对

## 情况 A：执行最后一步 git push 时提示报错？

如果提示 Updates were rejected because the remote contains work...，说明远程仓库里可能已经杂乱地存在一些文件。

安全解法：因为我们确定要用现在的本地文件作为最新的源码备份，可以使用强制推送（仅限这一次，且仅针对 *hexo-source* 分支）：
`git push -u origin hexo-source --force`

## 情况 B：提示需要登录

输入你的 GitHub 账号密码（或 Token）即可。
