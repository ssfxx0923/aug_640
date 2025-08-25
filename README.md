# Augment 教程网站

这是一个使用 Vercel 通过 GitHub 仓库自动部署的 Augment 账号使用教程网站。

## 🚀 部署步骤

### 方式一：通过 GitHub 仓库自动部署（推荐）

1. **创建 GitHub 仓库**
   - 在 GitHub 上创建一个新的公开仓库
   - 仓库名建议：`augment-tutorial` 或其他合适名称

2. **推送代码到 GitHub**
   ```bash
   # 添加远程仓库
   git remote add origin https://github.com/你的用户名/仓库名.git

   # 添加所有文件
   git add .

   # 提交更改
   git commit -m "Initial commit: Augment tutorial site"

   # 推送到 GitHub
   git push -u origin main
   ```

3. **连接 Vercel 和 GitHub**
   - 访问 [vercel.com](https://vercel.com)
   - 点击 "Import Project"
   - 选择 "From Git Repository"
   - 连接你的 GitHub 账户
   - 选择你的仓库
   - Vercel 会自动检测配置并部署

4. **获取域名并更新教程**
   - 部署完成后，Vercel 会提供一个域名（如：`augment-tutorial.vercel.app`）
   - 将教程.md 第11行的 `[你的vercel域名]` 替换为实际域名

### 方式二：手动部署

如果不使用 GitHub，也可以直接通过 Vercel CLI 部署：

```bash
# 安装 Vercel CLI
npm install -g vercel

# 登录
vercel login

# 部署
vercel --prod
```

## 📁 文件结构

```
augment/
├── index.html          # 主页面（教程内容）
├── public/
│   └── aug.rar        # 资源包文件
├── vercel.json        # Vercel 配置文件
├── package.json       # 项目配置
├── README.md          # 说明文档
├── 教程.md           # 原始 markdown 文件
└── 教程.html         # 原始 HTML 文件
```

## ⚙️ 配置说明

- **Vercel 配置** (`vercel.json`)：已优化为静态站点部署，无需构建步骤
- **静态资源**：`aug.rar` 文件放在 `public/` 目录下，部署后可直接访问
- **路由规则**：所有请求都会重定向到 `index.html`，实现单页应用效果

## 🔗 访问方式

部署完成后，你可以：

- 访问教程页面：`https://你的域名/`
- 下载资源包：`https://你的域名/aug.rar`

## 📝 更新教程

当需要更新教程内容时：

1. 编辑 `教程.md` 文件
2. 重新生成 `index.html`（如果需要）
3. 提交并推送到 GitHub
4. Vercel 会自动重新部署

## ⚠️ 重要提醒

- 确保 GitHub 仓库是公开的，以便 Vercel 能够访问
- 部署完成后，记得更新教程中的下载链接
- aug.rar 文件较大，首次部署可能需要一些时间
