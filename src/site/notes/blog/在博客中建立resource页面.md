---
{"dg-publish":true,"permalink":"/blog/resource/"}
---


# 核心思路
 
## 前端展示页：
在博客里建一个普通的页面（比如“资源下载”），列出所有文件。链接指向 redirect.html?id=文件ID。

## 后端逻辑页：
修改 redirect.html，让它读取 id，查表，然后跳转到对应的真实链接。

1. 创建文件
在博客根目录下，创建文件路径：source/downloads/redirect.html。
(如果 downloads 文件夹不存在，请先创建它)

2. 编写重定向代码
将以下代码复制到 redirect.html 中。你需要修改 targetUrl 变量为你真实的下载链接。

3. 阻止 Hexo 渲染 (关键步骤)
Hexo 默认会尝试解析所有的 HTML 文件并给它们加上博客的头部和底部（Header/Footer）。对于这个纯跳转页面，我们希望它保持原样，不要套用博客主题。

方法：
在 redirect.html 文件的最顶部添加 layout: false 的 Front-matter：

4. 部署与使用



```
---
layout: false
---
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>资源下载跳转中...</title>
    <style>
        body {
            font-family: "Lato", "PingFang SC", "Microsoft YaHei", sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background-color: #f5f7f9;
            color: #333;
        }
        .container {
            text-align: center;
            background: white;
            padding: 40px;
            border-radius: 5px;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            max-width: 400px;
            width: 90%;
        }
        .btn {
            display: inline-block;
            margin-top: 20px;
            padding: 10px 20px;
            background-color: #222;
            color: white;
            text-decoration: none;
            border-radius: 3px;
            transition: background 0.2s;
        }
        .btn:hover { background-color: #000; }
        .error { color: #d9534f; display: none; }
        .loading { display: block; }
    </style>
</head>
<body>
    <div class="container">
        <div id="loading-msg" class="loading">
            <h3>正在获取资源...</h3>
            <p>即将开始下载：<span id="file-name" style="font-weight:bold;">...</span></p>
            <p style="font-size: 12px; color: #999;">如果未自动跳转，请点击下方按钮</p>
            <a id="download-link" href="#" class="btn">立即下载</a>
        </div>
        
        <div id="error-msg" class="error">
            <h3>文件未找到</h3>
            <p>该资源链接可能已失效或参数错误。</p>
            <a href="/" class="btn">返回首页</a>
        </div>
    </div>

    <script>
        // ==========================================
        // 1. 配置你的文件列表 (ID : 真实链接)
        // ==========================================
        const fileMap = {
            // 格式： "ID": { url: "真实下载链接", name: "显示的文件名" }
            
            "calculus": {
                url: "https://github.com/ICEY4040727/HOME/releases/download/v1.0/calculus-notes.pdf",
                name: "高数笔记 (PDF)"
            },
            "c-guide": {
                url: "https://pan.baidu.com/s/xxxxxx", // 也可以是百度网盘链接
                name: "C语言入门指南 (ZIP)"
            },
            "trend-report": {
                url: "/downloads/report-2025.pdf", // 也可以是本地 source/downloads 下的文件
                name: "2025趋势报告"
            }
        };
        // ==========================================

        // 2. 获取 URL 中的 id 参数 (例如 ?id=calculus)
        const params = new URLSearchParams(window.location.search);
        const fileId = params.get('id');

        // 3. 执行跳转逻辑
        const resource = fileMap[fileId];
        
        if (resource) {
            // 找到文件，更新界面并跳转
            document.getElementById('file-name').innerText = resource.name;
            document.getElementById('download-link').href = resource.url;
            
            // 延迟 100ms 跳转，让用户稍微看一眼提示
            setTimeout(() => {
                window.location.href = resource.url;
            }, 500);
        } else {
            // 没找到文件，显示错误
            document.getElementById('loading-msg').style.display = 'none';
            document.getElementById('error-msg').style.display = 'block';
        }
    </script>
</body>
</html>
```

编辑页面：
打开 source/resources/index.md，写入以下内容：

```
---
title: 资源下载中心
date: 2025-12-25 12:00:00
type: "resources"
---

这里整理了我所有的学习资料和工具，点击即可下载。

## 📚 数学类
*   [📄 高等数学笔记 (PDF)](/downloads/redirect.html?id=calculus)
    *   包含微积分、级数等重点整理。

## 💻 编程类
*   [📦 C语言入门指南 (ZIP)](/downloads/redirect.html?id=c-guide)
    *   附带源码和练习题。

## 📊 其他
*   [📑 2025趋势报告](/downloads/redirect.html?id=trend-report)

> 如果下载链接失效，请在评论区留言。
```

如何添加新文件？
以后你要加新文件，只需要做两件事：

在 redirect.html 的 fileMap 里加一行
``"new-file": { url: "...", name: "新文件" }``

在 resources/index.md 里加一个链接：
``[下载新文件](/downloads/redirect.html?id=new-file)``


修改主题配置文件（添加菜单项）
打开 主题配置文件 themes/next/_config.yml。

搜索关键字 menu:。
在 menu: 下方添加一行 resources: /resources/ || fa fa-download。

配置中文翻译（让它显示为“资源下载”）
Next 主题支持国际化，如果你直接加了 resources，菜单上可能只会显示英文的 "resources" 或者空白（如果没找到翻译）。我们需要给它加个中文名。

打开 themes/next/languages/zh-CN.yml。
搜索 menu: 部分。
在下面添加一行 resources: 资源下载。