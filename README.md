# 网页红井测试版一键部署

网页红警一键部署包/chronodivide asssets。网页红井（网页版“红警”/Chronodivide）预览版测试站点，帮助各类爱好者一键搭建自己的网页版“红警”站点，助力营销和知识分享

## 赞助商

本项目的CDN加速和安全防护由腾讯EdgeOne赞助

[![最佳亚洲 CDN、Edge 和安全解决方案 - 腾讯 EdgeOne](https://edgeone.ai/media/34fe3a45-492d-4ea4-ae5d-ea1087ca7b4b.png)](https://edgeone.ai/?from=github)

## 一键部署

### Github托管页面

fork该项目，命名为 你的名字.github.io，例如 ra2web.github.io

正如你所见，这个项目的名字就符合这个域名规则。那么，此时的你可以访问 https://ra2web.github.io 来游玩网页红井拉

当前本项目同样可以通过github pages访问，地址就是 https://ra2web.github.io

### 腾讯云EdgeOne Pages

[![使用 EdgeOne Pages 部署](https://cdnstatic.tencentcs.com/edgeone/pages/deploy.svg)](https://edgeone.ai/pages/new?repository-url=https%3A%2F%2Fgithub.com%2Fra2web%2Fra2web.github.io)

### Vercel

[![一键部署到Vercel](https://vercel.com/button)](https://vercel.com/import/project?template=https://github.com/ra2web/ra2web.github.io)

### Cloudflare

本项目是纯静态站点（无需构建步骤），可以直接部署到 Cloudflare Pages 或 Cloudflare Workers。

#### 方式一：Cloudflare Pages（推荐，图形界面操作）

1. 将本仓库推送到 GitHub
2. 打开 Cloudflare Dashboard → **Workers & Pages** → **Create application** → **Pages**
3. 连接你的 GitHub 仓库并选择仓库
4. 构建设置：
   - Framework preset：`None`
   - Build command：留空
   - Build output directory：`./`（项目根目录）
5. 点击 **Save and Deploy**

#### 方式二：Cloudflare Workers（静态资源，命令行部署）

仓库已内置 `wrangler.toml`，一条命令即可完成部署：

```bash
npx wrangler deploy
```

说明：

- `wrangler.toml` 把项目根目录作为静态资源目录（`assets.directory = "./"`），游戏运行时会从站点根目录加载 `config.ini`、`servers.ini`、`mods.ini`
- `.assetsignore` 用于排除无需上线的文件（如 `.git`、cPanel 残留页面等）
- `_headers` 用于设置缓存响应头，Cloudflare Pages 与 Workers 均支持



