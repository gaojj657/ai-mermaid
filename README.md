# Mermaid AI 智能编辑器

一个基于 Vue 3 和 Mermaid 的智能图表编辑器，支持 AI 自动修复和优化 Mermaid 代码。

## 功能特性

- 📝 实时预览 Mermaid 图表
- 🤖 AI 自动修复语法错误
- ✨ AI 优化/重写图表代码
- 💾 导出 SVG/JPG 格式
- 🧠 智能修复记忆库

## 本地使用

1. 克隆或下载此仓库
2. 复制 `config.js.example` 为 `config.js`
3. 在 `config.js` 中填写您的阿里云 DashScope API Key
4. 直接在浏览器中打开 `mermaid-editor.html`

## GitHub Pages 部署

### 方法一：使用 GitHub Pages（推荐）

1. 将项目推送到 GitHub 仓库
2. 在仓库设置中启用 GitHub Pages
   - 进入 Settings → Pages
   - Source 选择 `main` 分支（或你的主分支）
   - 点击 Save
3. 访问 `https://你的用户名.github.io/仓库名/mermaid-editor.html`

### 方法二：将 HTML 文件设为首页

如果希望直接访问域名就能打开编辑器：

1. 将 `mermaid-editor.html` 重命名为 `index.html`
2. 推送到 GitHub
3. 启用 GitHub Pages
4. 访问 `https://你的用户名.github.io/仓库名/`

### 注意事项

⚠️ **重要**：`config.js` 文件包含 API Key，已添加到 `.gitignore`，不会被提交到 GitHub。

如果要在 GitHub Pages 上使用，需要：

1. **方案 A**：在 GitHub 仓库中手动创建 `config.js`（通过网页界面）
   - 进入仓库 → Add file → Create new file
   - 文件名：`config.js`
   - 内容：复制 `config.js.example` 的内容并填入你的 API Key
   - 提交文件

2. **方案 B**：使用环境变量（需要后端支持，GitHub Pages 不支持）

3. **方案 C**：在 HTML 中直接配置（不推荐，API Key 会暴露）
   - 修改 `mermaid-editor.html`，将 API Key 直接写在代码中
   - ⚠️ 注意：这会暴露你的 API Key，任何人都可以看到

## 技术栈

- Vue 3
- Mermaid.js
- Tailwind CSS
- 阿里云 DashScope API (Qwen)

## 文件说明

- `mermaid-editor.html` - 主页面文件
- `config.js` - 配置文件（包含 API Key，不提交到 Git）
- `config.js.example` - 配置文件模板
- `memory.js` - AI 修复记忆库
- `favicon.png` / `favicon1.png` - 网站图标

## 许可证

MIT License

