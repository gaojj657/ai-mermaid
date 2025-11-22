# Mermaid AI 智能编辑器

一个基于 Vue 3 和 Mermaid 的智能图表编辑器，支持 AI 自动修复和优化 Mermaid 代码。

## 🌐 在线体验

在线体验网址：https://gaojj657.github.io/ai-mermaid/mermaid-editor.html

## 功能特性

### 📝 实时预览
- 输入 Mermaid 代码后自动渲染预览（500ms 防抖优化）
- 支持流程图、序列图、甘特图等多种图表类型
- 实时显示渲染状态和错误信息

### 🤖 AI 自动修复
- 智能识别 Mermaid 语法错误
- 基于错误信息自动修复代码
- 支持迭代修复，最多尝试 5 次直到成功
- 自动生成修复总结，记录修复经验到记忆库

### ✨ AI 优化/重写
- 根据你的需求优化现有图表
- 支持复杂化、添加样式、重构等操作
- 使用自然语言描述优化需求即可

### 💾 导出功能
- 支持导出为 SVG 格式（矢量图，无损缩放）
- 支持导出为 JPG 格式（高质量图片）
- 一键下载，方便分享和使用

### 🧠 智能记忆库
- 自动记录修复经验，提升后续修复准确率
- 支持本地文件记忆和浏览器本地存储记忆
- 修复历史可参考，避免重复错误

## 本地使用

1. 克隆或下载此仓库
2. 复制 `config.js.example` 为 `config.js`
3. 在 `config.js` 中填写您的阿里云 DashScope API Key
4. 直接在浏览器中打开 `mermaid-editor.html`

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

