---
{"dg-publish":true,"permalink":"/blog/configure-a-scheduled-run-of-git-hub-actions-in-the-trend-radar-git-hub-repository-eliminating-the-need-to-update-during-local-hexo-g/","created":"2025-12-25T12:40:09.630+08:00","updated":"2025-12-25T16:12:00.067+08:00"}
---


# 创建一个 GitHub Actions 工作流文件。

## 1. 创建工作流文件

在你的 TrendRadar 仓库根目录下，创建 .github/workflows/auto_update.yml 文件
```
name: Auto Update News

on:
  schedule:
    # 每 6 小时运行一次 (UTC 时间)
    - cron: '0 */6 * * *'
  workflow_dispatch: # 允许手动触发

jobs:
  update:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout code
        uses: actions/checkout@v3

      - name: Set up Python
        uses: actions/setup-python@v4
        with:
          python-version: '3.9'

      - name: Install dependencies
        run: |
          pip install -r requirements.txt

      - name: Run TrendRadar
        run: |
          python main.py

      - name: Commit and Push changes
        run: |
          git config --local user.email "github-actions[bot]@users.noreply.github.com"
          git config --local user.name "github-actions[bot]"
          git add .
          git commit -m "Auto update news: $(date)" || exit 0
          git push
```

## 2. 开启仓库权限

为了让 GitHub Actions 能够将更新后的数据推送到你的仓库，你需要开启写入权限：

- 进入你的 TrendRadar 仓库 Settings。
- 点击左侧 Actions -> General。
- 拉到最下方 Workflow permissions。
- 选择 Read and write permissions。
- 点击 Save。

## 3. 效果说明

- 自动运行：GitHub 每 6 小时会自动运行一次爬虫。
- 自动部署：如果你的 TrendRadar 开启了 GitHub Pages，每次 git push 后GitHub Pages 会自动重新构建。
- 无需本地操作：你的 Hexo 博客通过 iframe 引用的是这个在线地址，因此侧边栏内容会自动更新，无需你本地运行 hexo g。

