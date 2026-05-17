# 🚀 快速部署指令

## ⚡ 一鍵複製命令（替換 YOUR_USERNAME）

### 如果您還沒有 GitHub Repository

1️⃣ **前往 GitHub 建立新 Repository**
   - 登入 https://github.com
   - 點擊右上角 `+` → `New repository`
   - Repository name: `apqp-ppap-system`
   - 選擇 Public 或 Private
   - ⚠️ **不要勾選** "Initialize this repository with a README"
   - 點擊 `Create repository`

2️⃣ **執行以下命令（替換 YOUR_USERNAME）**

```bash
# 設定遠端 Repository（請替換 YOUR_USERNAME）
cd /home/claude/apqp-ppap-system
git remote add origin https://github.com/YOUR_USERNAME/apqp-ppap-system.git

# 推送到 GitHub
git push -u origin main
```

### 如果您已經有 GitHub Repository

```bash
# 直接推送
cd /home/claude/apqp-ppap-system
git remote add origin https://github.com/YOUR_USERNAME/apqp-ppap-system.git
git push -u origin main
```

---

## ✅ 驗證上傳成功

前往以下網址確認（替換 YOUR_USERNAME）：
```
https://github.com/YOUR_USERNAME/apqp-ppap-system
```

您應該會看到：
- ✅ index.html
- ✅ README.md
- ✅ QUICK_START.md
- ✅ GITHUB_DEPLOY.md
- ✅ LICENSE
- ✅ .gitignore

---

## 🌐 啟用 GitHub Pages（免費網站託管）

1. 進入 Repository → `Settings` → `Pages`
2. Source 選擇：
   - Branch: `main`
   - Folder: `/ (root)`
3. 點擊 `Save`
4. 等待 1-2 分鐘

您的網站將發布於：
```
https://YOUR_USERNAME.github.io/apqp-ppap-system/
```

---

## 🔄 日後更新流程

當您修改程式碼後：

```bash
cd /home/claude/apqp-ppap-system

# 查看變更狀態
git status

# 加入所有變更
git add .

# 提交變更
git commit -m "更新描述"

# 推送到 GitHub
git push
```

---

## 📦 打包下載（備份用）

如果您想下載整個專案資料夾：

```bash
# 建立壓縮檔
cd /home/claude
tar -czf apqp-ppap-system.tar.gz apqp-ppap-system/

# 或使用 ZIP
zip -r apqp-ppap-system.zip apqp-ppap-system/
```

---

## 🆘 遇到問題？

### 錯誤 1: "Permission denied (publickey)"

**解決方法**：使用 HTTPS 而非 SSH
```bash
git remote set-url origin https://github.com/YOUR_USERNAME/apqp-ppap-system.git
```

### 錯誤 2: "Authentication failed"

**解決方法**：使用 Personal Access Token
1. GitHub → Settings → Developer settings → Personal access tokens
2. Generate new token (classic)
3. 勾選 `repo` 權限
4. 複製 Token
5. 當 git push 要求密碼時，貼上 Token（不是 GitHub 密碼）

### 錯誤 3: "Repository not found"

**解決方法**：檢查 Repository 名稱和 URL
```bash
git remote -v
# 確認顯示正確的 URL
```

---

## 📧 技術支援

- 查看完整教學: [GITHUB_DEPLOY.md](GITHUB_DEPLOY.md)
- 使用者指南: [QUICK_START.md](QUICK_START.md)
- 專案說明: [README.md](README.md)

---

**目前狀態**: ✅ 專案已完成 Git 初始化，準備推送到 GitHub

**下一步**: 執行上方的 `git remote add origin` 命令即可上傳！
