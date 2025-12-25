---
{"dg-publish":true,"permalink":"/blog/hexo-github-page/","created":"2025-12-15T03:24:25.523+08:00","updated":"2025-12-25T16:11:24.939+08:00"}
---


# 部署
## 第一步：创建 GitHub 仓库

登录你的 GitHub。

点击右上角的 + 号 -> New repository。

Repository name (仓库名) 填写：

格式必须是：你的用户名.github.io

(注意：如果名字不对，GitHub Pages 不会作为主站生效)

选择 Public。

点击 Create repository。

## 第二步：安装 Hexo 部署插件

在你的博客根目录（BLOG）下打开终端，运行：

```
npm install hexo-deployer-git --save
```

## 第三步：修改站点配置文件

打开博客根目录下的 _config.yml 文件（不是主题的配置文件），拉到最底部，找到 deploy: 部分。

修改为以下内容（注意缩进和冒号后的空格）：

```
# Deployment
## Docs: https://hexo.io/docs/one-command-deployment
deploy:
  type: git
  repo: https://github.com/你的用户名/你的用户名.github.io.git
  branch: main
```

- 注意 1：把 你的用户名 换成你真实的 GitHub 用户名。

- 注意 2：现在的 GitHub 默认分支通常是 main，以前是 master。如果你不确定，可以在 GitHub 仓库页面看一眼分支名。

## 第四步：生成并部署

在终端中依次运行以下命令：

清理缓存（防止样式没更新）：
```
hexo clean
```
生成静态文件：
```
hexo g
```
部署到 GitHub：
```
hexo d
```

首次部署时：
终端可能会弹出一个登录窗口，或者要求你输入 GitHub 的用户名和密码（现在通常需要使用 Personal Access Token，或者直接在弹出的浏览器窗口授权）。按照提示操作即可。

## 第五步：验证

等待几分钟（GitHub Pages 首次构建可能需要 1-5 分钟）。

在浏览器访问：https://你的用户名.github.io

# 备份源码

手动备份源码
为了数据安全，建议你建立一个独立的分支（比如叫 hexo-source）来专门存放源码。

操作流程如下：

初始化本地仓库（仅需一次）：

```
git init
git remote add origin https://github.com/你的用户名/你的用户名.github.io.git
```

创建并切换到源码分支：

```
git checkout -b hexo-source
```

日常备份源码（每次写完文章后）：

```
git add .
git commit -m "备份源码"
git push origin hexo-source
```

### 第一步：检查并配置忽略文件（至关重要）

在执行 Git 命令前，必须确保我们不备份垃圾文件（如生成的网页和依赖包）。

在博客根目录 BLOG 下，检查是否存在名为 .gitignore 的文件。
如果没有，请新建一个文本文件命名为 .gitignore。
确保文件内包含以下内容（如果没有，请复制粘贴进去）：
```
.DS_Store
Thumbs.db
db.json
*.log
node_modules/
public/
.deploy_git/
```

### 第二步：处理主题文件夹的 Git 冲突（关键）

你修改了 next 里的样式。通常 next 也是一个 Git 仓库（如果你是克隆下来的）。如果不处理，你的主仓库无法备份主题里的修改。

请在文件资源管理器中打开 next：

查看是否有隐藏的 .git 文件夹？
如果有，请直接删除这个 .git 文件夹。
解释：这样做是把主题变成你项目的一部分，而不是一个独立的子仓库，确保你的 custom.styl 修改能被备份。

### 第三步：执行“无损”备份命令

请在 BLOG 根目录下打开终端，逐行执行以下命令。我会解释每一行的作用，确保你放心。

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