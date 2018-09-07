# 搭建一个免费的，无限流量的 Blog

- [阮一峰:搭建一个免费的，无限流量的Blog----github Pages和Jekyll入门](http://www.ruanyifeng.com/blog/2012/08/blogging_with_jekyll.html)
- [使用hexo+github pages快速搭建个人博客](https://segmentfault.com/a/1190000005013053)
- [如何使用 Hexo 和 GitHub Pages 搭建这个博客](https://uchuhimo.me/2017/04/11/genesis/)

Hexo 是一个基于 Nodejs 快速简洁高效的博客框架，Hexo 使用 Markdown 语法来编辑文章，只需要几秒钟的时间就可以成生静态的网页。整个系统就是一个博客系统。

一个博客的搭建过程分为三步：

- 编写：包含内容的书写与格式的配置 (使用 Markdown，内置大量层级、列表、超链接、代码等的简便语法支持)
- 构建：从编写的原始内容生成可发布的最终内容 (使用 Hexo，几条命令完成生成、预览、发布步骤)
- 发布：让待发布的内容对读者可见 (使用 GitHub Pages 进行托管，方便又免费)

## 环境准备

### 安装 Node.js

官网下载：https://nodejs.org/en/download/

### 安装 Hexo

```sh
npm install -g hexo-cli
```

#### 常用 Hexo 命令

- 初始化目录：hexo init [folder]
- 新建文章：hexo new [layout] <title> 或 hexo n [layout] <title> 
- 新建草稿：hexo new draft <title>
- 将草稿发布为正式文章：hexo publish <title>
- 生成静态文件：hexo generate 或 hexo g 
- 监听文件变化：hexo g --watch 或 hexo g -w
- 部署：hexo deploy 或 hexo d 
- 先生成后部署：hexo d -g
- 启动本地服务器（服务器会监听文件变化并自动更新）：hexo server 或 hexo s 
- 启动调试：hexo s --debug
- 预览草稿：hexo s --draft
- 清除缓存：hexo clean

## 使用 NexT 主题

下载主题

```sh
cd <your-hexo-site>
git clone https://github.com/iissnan/hexo-theme-next themes/next
```

### 配置 `_config.yml`

```yaml
theme: next,
language: zh-Hans
```

### 查看是否生效

```sh
hexo clean
hexo generate
hexo server
```


## [Hexo 中文文档](https://hexo.io/zh-cn/docs/)

### [配置](https://hexo.io/zh-cn/docs/configuration.html)