+++
title = '常用hugo命令'
date = 2024-11-25T19:05:27+08:00
draft = false
summary = "hugo常用命令"
author = "Justin"
tags = ["hugo","space"]
+++


以下是以 Markdown 格式书写的 Hugo 常用命令说明：

# Hugo 常用命令

## 常用命令

- 创建文件：`hugo new posts/<post-name>.md`
- 发布文件：`hugo new posts/<post-name>.md --editor <justin>`
- 构建网站：`hugo`
- 清理缓存：`hugo --cleanDestinationDir`

## 更多命令
### 1. 创建新站点

```bash
hugo new site <site-name>
生成一个新的 Hugo 项目。
```

**克隆主题**

Hugo 的主题通常托管在 GitHub 上，可以通过以下命令克隆：
```bash
git clone https://github.com/<theme-repository> themes/<theme-name>
```
或者参考主题官方文档进行安装。

### 2. 启动本地服务器

**本地开发预览**
```bash
hugo server -D
```
- -D: 包括草稿（draft）内容。 
- 地址为 http://localhost:1313。

## 3. 创建内容

创建新文章
```bash
hugo new posts/<post-name>.md
```
默认会将草稿状态设置为 true。

发布文章

将文章的 draft 属性修改为 false，或者直接用以下命令创建并编辑：
```bash
hugo new posts/<post-name>.md --editor <your-editor>
```
## 4. 构建静态网站

生成静态文件
```bash
hugo
```

- 默认生成在 public 文件夹中。
- 可使用 --minify 压缩生成的静态文件：

```bash
hugo --minify
```


指定输出目录
```bash
hugo -d <output-directory>
```
## 5. 配置和调试

检查配置
```bash
hugo config
```
调试模式
```bash
hugo server --debug
```
## 6. 清理生成文件

清除缓存
```bash
hugo --cleanDestinationDir
```
## 7. 其他命令

查看 Hugo 版本
```bash
hugo version
```
列出所有可用命令
```bash
hugo help
```
列出指定命令的详细帮助
```bash
hugo help <command>
```
列出站点中所有内容
```bash
hugo list all
```
列出草稿内容
```bash
hugo list drafts
```

