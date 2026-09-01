# 周乐琪 · 个人简历网站

一个纯静态的个人简历网站，支持互联网/金融双版本切换，可直接部署到 GitHub Pages。

## 特性

- 🎨 极简优雅设计风格，大量留白
- 🔄 双版本切换（互联网方向 / 金融方向）
- 📱 响应式设计，适配手机和电脑
- ⚡ 纯静态单文件，无需构建工具，加载极快
- 🖨️ 支持打印为 PDF
- 🔍 SEO 友好

## 文件结构

```
zhouleqi-resume/
├── index.html      # 主页面（包含所有 HTML/CSS/JS）
├── CNAME           # 自定义域名配置（zhouleqi.com）
├── .nojekyll       # 禁用 GitHub Pages 的 Jekyll 处理
└── README.md       # 说明文档
```

## 部署到 GitHub Pages

### 方法一：手动上传（最简单）

1. 在 GitHub 新建一个仓库，命名为 `你的用户名.github.io`（例如 `zhouleqi.github.io`）
2. 把本目录下的所有文件上传到仓库根目录
3. 进入仓库 Settings → Pages
4. Source 选择 `Deploy from a branch`，Branch 选择 `main` / `master`，文件夹选择 `/ (root)`
5. 点击 Save，等待 1-2 分钟，网站即可通过 `https://你的用户名.github.io` 访问

### 方法二：使用 Git 命令行

```bash
# 1. 进入项目目录
cd zhouleqi-resume

# 2. 初始化 Git 仓库
git init
git add .
git commit -m "Initial commit: personal resume website"

# 3. 关联 GitHub 远程仓库（先在 GitHub 创建好空仓库）
git remote add origin https://github.com/你的用户名/你的用户名.github.io.git
git branch -M main
git push -u origin main

# 4. 在 GitHub 仓库 Settings → Pages 中启用 Pages
```

## 配置自定义域名 zhouleqi.com

### 1. GitHub 端设置
- 仓库 Settings → Pages → Custom domain 填入 `zhouleqi.com`
- 勾选 Enforce HTTPS

### 2. 域名注册商端 DNS 配置
在你的域名管理平台（阿里云/腾讯云/Cloudflare 等）添加以下记录：

| 类型 | 主机记录 | 记录值 |
|------|---------|--------|
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |
| CNAME | www | 你的用户名.github.io |

> 本项目的 `CNAME` 文件已配置好 `zhouleqi.com`，上传后 GitHub 会自动识别。

DNS 生效通常需要几分钟到几小时，生效后即可通过 `https://zhouleqi.com` 访问。

## 本地预览

直接用浏览器打开 `index.html` 即可预览，无需任何服务器。

或者使用简单的本地服务器：

```bash
python3 -m http.server 8000
# 然后访问 http://localhost:8000
```

## 修改内容

所有内容都在 `index.html` 中：
- 简历文字：搜索对应文字直接修改
- 颜色主题：修改 `<style>` 中的 `:root` CSS 变量
- 版本切换内容：搜索 `exp-internet` 和 `exp-finance` 分别修改

## 技术栈

- 纯 HTML5 + CSS3 + 原生 JavaScript
- Google Fonts（Inter + Noto Serif SC）
- 无任何框架依赖，无构建步骤
