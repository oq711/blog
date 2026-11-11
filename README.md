# blog

个人博客，基于 [Hexo](https://hexo.io/zh-cn/) 8 + GitHub Pages 搭建。

- 线上地址：<https://oq711.github.io/blog/>
- 主题：[Butterfly](https://butterfly.js.org/) 5.7.2（通过 npm 安装，配置在 `_config.butterfly.yml`）

## 本地开发

```bash
npm install          # 首次安装依赖
npm run server       # 本地预览：http://localhost:4000/blog/
npm run build        # 生成静态文件到 public/
npm run clean        # 清理缓存和 public/
```

> 注意：`_config.yml` 里配置了 `root: /blog/`，所以本地预览地址也带 `/blog/` 前缀，
> 这样本地和线上的资源路径行为保持一致。

## 写文章

```bash
npx hexo new post "文章标题"
```

生成的文件在 `source/_posts/`，编辑 front-matter 和正文即可。新建独立页面用：

```bash
npx hexo new page "about"
```

## 发布

推送到 `main` 分支即可，`.github/workflows/pages.yml` 会自动构建并部署到 GitHub Pages：

```bash
git add .
git commit -m "post: 文章标题"
git push
```

部署进度在仓库的 **Actions** 页查看；首次部署前需要在
**Settings → Pages → Build and deployment → Source** 选择 **GitHub Actions**。

## 目录说明

```
_config.yml             站点主配置（标题、url、主题等）
_config.landscape.yml   主题配置覆盖，升级主题不会丢
scaffolds/              新建文章/页面的模板
source/_posts/          文章正文
source/                 图片、CNAME 等静态资源
themes/                 自定义主题放这里（当前主题来自 node_modules）
public/                 构建产物，已 gitignore
```
