---
title: 用 Hexo + GitHub Pages 搭一个博客
date: 2026-11-10 21:00:00
tags:
  - Hexo
  - GitHub Pages
categories:
  - 折腾记录
---

这是本站的第一篇文章，顺便当作「这个博客是怎么搭起来的」的说明文档。

## 为什么选 Hexo

Hexo 是一个静态站点生成器：你只写 Markdown，它把文章编译成纯 HTML/CSS/JS，再由 GitHub Pages 免费托管。
没有数据库、没有服务器、没有续费，写作体验就是一个 Markdown 编辑器加上几条命令。

> 生成链路：Markdown + 主题模板 → `hexo generate` → `public/` → GitHub Pages

## 本地怎么跑

```bash
npm install        # 安装依赖
npm run server     # 本地预览 http://localhost:4000/blog/
npm run build      # 生成静态文件到 public/
```

## 怎么写新文章

```bash
npx hexo new post "文章标题"
```

然后编辑 `source/_posts/` 下新生成的 Markdown 文件，顶部那段 front-matter 控制标题、时间、标签和分类：

| 字段 | 作用 |
| --- | --- |
| `title` | 文章标题 |
| `date` | 发布时间，决定排序 |
| `tags` | 标签，可多个 |
| `categories` | 分类，有层级 |

## 怎么发布

把改动 push 到 `main` 分支，GitHub Actions 会自动构建并发布到 Pages，全程不用管服务器。

```yaml
# 简化版流程
git add .
git commit -m "post: 标题"
git push
```

就这样，写作即发布。
