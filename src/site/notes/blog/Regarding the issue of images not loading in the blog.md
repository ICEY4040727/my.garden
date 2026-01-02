---
{"dg-publish":true,"permalink":"/blog/regarding-the-issue-of-images-not-loading-in-the-blog/","created":"2025-12-12T11:20:50.993+08:00","updated":"2025-12-25T16:11:27.744+08:00"}
---


# 种类

### 正文中无法加载

#### 浏览器右键图像 $\Rightarrow$ 复制图像链接来查看解析出的图像链接是否与你的图片路径一致

##### 不一致：

卸载旧插件
	`npm uninstall hexo-asset-image`

安装修复版插件（推荐）：
安装这个目前社区反馈最好的修复版
	`npm install https://github.com/CodeFalling/hexo-asset-image --save`

*这是直接从 GitHub 安装 CodeFalling 维护的版本，比 npm 上的旧版本好用*

