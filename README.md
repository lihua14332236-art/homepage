# Personal Homepage

极简风格个人主页，参考 Notion 设计语言构建。单文件静态页面，零依赖，开箱即用。

## 项目结构

```
.
├── index.html          # 主页面（唯一核心文件）
└── .github/
    └── workflows/
        └── deploy.yml  # GitHub Actions 自动部署
```

## 快速开始

### 本地预览

直接用浏览器打开 `index.html`，或使用任意本地服务器：

```bash
# Python 3
python -m http.server 8080

# Node.js (npx serve)
npx serve .
```

### 部署到 GitHub Pages (推荐)

1. 将代码推送到 GitHub 仓库
2. 进入仓库 **Settings → Pages**
3. **Source** 选择 **GitHub Actions**
4. 推送 `main` 分支，Actions 会自动构建部署
5. 访问 `https://你的用户名.github.io/仓库名`

首次使用需确保 Settings → Actions → General → Workflow permissions 为 **Read and write permissions**。

### 部署到 Cloudflare Pages

1. 登录 [Cloudflare Dashboard](https://dash.cloudflare.com)
2. 进入 **Workers & Pages → Pages → 创建项目**
3. 连接 GitHub 仓库
4. 构建设置：
   - **构建命令**：留空
   - **输出目录**：`.`（或 `/`）
5. 点击部署

## 个性化修改

打开 `index.html`，搜索以下关键字即可快速定位：

| 内容 | 搜索关键字 | 说明 |
|------|-----------|------|
| 页面标题 | `<title>` | 浏览器标签页标题 |
| 姓名 | `Lin Meng` / `林梦` | 多处出现，建议全局替换 |
| 岗位/身份 | `设计驱动思考` | Hero 区大标题 |
| 个人简介 | `设计专业在读学生` | Hero 区副标题 |
| 关于我 | `关于我` | 关于我段落文字 |
| 项目卡片 | `乐享` / `山隐` / `MeetNode` | 作品集项目名和描述 |
| 技能标签 | `Figma` / `Sketch` | 技能列表 |
| 联系方式 | `linmeng@example.com` | 邮箱地址 |
| 社交链接 | `Dribbble` / `Behance` / `GitHub` | 社交链接 |
| 主要颜色 | `--text` / `--bg` | CSS 变量，见 `:root` |

## 日常运维

### 更新内容

直接编辑 `index.html`，提交并推送到 `main` 分支，GitHub Actions 会自动重新部署。部署进度可在仓库 **Actions** 标签页查看。

### 自定义域名

**GitHub Pages：**
1. 在 Settings → Pages → Custom domain 填入域名
2. 在 DNS 服务商添加 CNAME 记录指向 `你的用户名.github.io`
3. Actions 部署后生效

**Cloudflare Pages：**
1. 进入 Pages 项目 → Custom domains
2. 按指引配置 DNS（Cloudflare 管理的域名会自动配置）

### 常见问题

**部署失败？**
- 检查 Settings → Pages → Source 是否选择了 GitHub Actions
- 检查 Actions 权限：Settings → Actions → General → Read and write permissions

**修改后页面不更新？**
- 浏览器强制刷新（Ctrl + F5 / Cmd + Shift + R）
- GitHub Pages 部署通常 1-2 分钟内生效

**需要 HTTPS？**
- GitHub Pages 和 Cloudflare Pages 均自动提供免费 HTTPS 证书，无需额外配置

## 技术栈

- 纯静态 HTML / CSS / JS
- 零框架、零构建步骤
- 谷歌字体（Inter + Noto Sans SC）
- 响应式设计，适配移动端
