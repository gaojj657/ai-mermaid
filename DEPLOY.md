# GitHub Pages 部署指南

## 目标
- **GitHub 仓库页面**：用于下载代码，不包含 `config.js`（通过 `.gitignore` 隐藏）
- **GitHub Pages 在线体验**：包含 API Key，可以直接使用

## 方案一：在 GitHub 网页上手动创建 config.js（推荐）

### 步骤：

1. **访问你的仓库**：https://github.com/gaojj657/ai-mermaid

2. **创建 config.js 文件**：
   - 点击仓库页面右上角的 **"Add file"** → **"Create new file"**
   - 文件名输入：`config.js`
   - 在编辑器中粘贴以下内容（替换为你的 API Key）：
   ```javascript
   // 配置文件
   // 请在此处填写您的阿里云 DashScope API Key
   window.APP_CONFIG = {
       DASHSCOPE_API_KEY: '你的API-Key-这里'
   };
   ```

3. **提交文件**：
   - 滚动到页面底部
   - 在 "Commit new file" 部分，填写提交信息：`Add config.js for GitHub Pages`
   - 点击 **"Commit new file"**

4. **启用 GitHub Pages**：
   - 进入仓库 → **Settings** → **Pages**
   - **Source** 选择 `main` 分支，文件夹选择 `/ (root)`
   - 点击 **Save**

5. **等待生效**（1-2 分钟），然后访问：
   ```
   https://gaojj657.github.io/ai-mermaid/mermaid-editor.html
   ```

### 优点：
- ✅ 简单快速
- ✅ 不需要维护多个分支
- ✅ 代码和部署在同一仓库

### 注意事项：
- ⚠️ `config.js` 会出现在 GitHub 仓库中，但只有你能看到和编辑
- ⚠️ 如果仓库是公开的，API Key 会暴露（建议使用私有仓库或限制 API Key 权限）

---

## 方案二：使用独立的 gh-pages 分支（更安全）

### 步骤：

1. **创建 gh-pages 分支并包含 config.js**：
   ```powershell
   # 创建新分支
   git checkout -b gh-pages
   
   # 临时移除 .gitignore 中的 config.js（或直接添加）
   # 注意：config.js 已经在本地存在
   
   # 强制添加 config.js（即使它在 .gitignore 中）
   git add -f config.js
   
   # 提交
   git commit -m "Add config.js for GitHub Pages deployment"
   
   # 推送到远程
   git push origin gh-pages
   ```

2. **在 GitHub 设置中**：
   - 进入 **Settings** → **Pages**
   - **Source** 选择 `gh-pages` 分支
   - 点击 **Save**

3. **切换回 main 分支**：
   ```powershell
   git checkout main
   ```

### 优点：
- ✅ 代码和部署完全分离
- ✅ main 分支不包含敏感信息
- ✅ 更符合最佳实践

### 缺点：
- ⚠️ 需要维护两个分支
- ⚠️ 更新代码时需要同步到 gh-pages 分支

---

## 推荐方案

**建议使用方案一**，因为：
1. 更简单，不需要维护多个分支
2. 如果你的仓库是私有的，API Key 不会暴露
3. 即使仓库是公开的，你也可以：
   - 使用限制权限的 API Key
   - 设置 API Key 的使用限制（IP、域名等）
   - 定期轮换 API Key

## 验证部署

部署成功后，访问：
```
https://gaojj657.github.io/ai-mermaid/mermaid-editor.html
```

如果页面正常加载且 AI 功能可用，说明部署成功！

