# DeepCybo 官方静态站点（GitHub Pages）

本仓库包含北京机智赛博智能科技有限公司（DeepCybo）的企业静态页面，适配 GitHub Pages 与自定义域名 `deepcybo.site`。

## 目录结构
- `index.html`：主页
- `assets/css/styles.css`：样式
- `assets/img/logo.svg`：Logo
- `favicon.svg`：站点图标
- `.nojekyll`：禁用 Jekyll 处理（保留下划线目录与静态资源）
- `robots.txt` / `sitemap.xml`：SEO 相关
- `CNAME`：自定义域配置

## 本地预览
```bash
# 任意静态服务器均可
python3 -m http.server 5500
# 打开 http://localhost:5500
```

## 部署到 GitHub Pages
1. 将本目录作为仓库推送：
   ```bash
   git init
   git add .
   git commit -m "init: deepcybo.site static site"
   git branch -M main
   git remote add origin git@github.com:<your-account>/deepcybo.site.git
   git push -u origin main
   ```
2. 在 GitHub 仓库设置中开启 Pages：
   - Settings → Pages → Branch 选择 `main` 分支 `/ (root)` → Save。
3. 自定义域名（可选，已提供 `CNAME`）：
   - DNS 添加 A 记录指向：`185.199.108.153`、`185.199.109.153`、`185.199.110.153`、`185.199.111.153`
   - 或添加 `CNAME` 记录：`deepcybo.site` → `<your-account>.github.io`
   - 勾选 Enforce HTTPS，等待证书颁发。

## 修改站点基础信息
- 如果使用子路径（如 `<your-account>.github.io/repo`），请保持 `index.html` 中资源使用相对路径（已处理）。
- 如需更换域名：
  - 更新 `CNAME`、`robots.txt` 中的 `Sitemap`、`sitemap.xml` 的 `<loc>` 与 `index.html` 中的 `canonical`/`og:url`/JSON-LD `url`。

## 许可
© 北京机智赛博智能科技有限公司。保留所有权利。
