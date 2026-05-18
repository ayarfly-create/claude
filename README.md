# APQP/PPAP 文件管理系統

> 專為金屬精密沖壓業設計的 APQP 第三版 / PPAP 文件管理系統

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![React](https://img.shields.io/badge/React-18-61DAFB?logo=react)](https://reactjs.org/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind-3-38B2AC?logo=tailwind-css)](https://tailwindcss.com/)

## 📋 系統簡介

這是一個全面的 APQP/PPAP 文件管理系統，遵循 **APQP 第三版 (2024)** 標準，專為汽車零件供應商的金屬精密沖壓業務設計。

### 核心功能

- ✅ **多專案管理** - 同時追蹤多個零件的 APQP 進度
- ✅ **APQP 五階段追蹤** - 完整的階段鎖定與審核機制
- ✅ **PPAP 18項查核** - 符合汽車業標準的提交要求
- ✅ **四級權限系統** - 管理員/主管/組員/訪客
- ✅ **CFT 權責矩陣** - 業務/工程/品保/生產部門協作
- ✅ **文件上傳管理** - 支援 JPG/PNG/PDF 格式
- ✅ **三語系介面** - 繁體中文 / English / ภาษาไทย
- ✅ **進度視覺化** - 儀表板即時顯示專案狀態
- ✅ **PSW 封面管理** - 零件淨重 4 位小數驗證
- ✅ **設備關聯追蹤** - 200T沖床 / OMM量測儀管理

## 🚀 快速開始

### 線上預覽

直接在瀏覽器開啟 `index.html` 即可使用（無需安裝任何依賴）

### 本地運行

```bash
# 1. 複製專案
git clone https://github.com/ayarfly-create/aqpq-ppap-system.git
cd aqpq-ppap-system

# 2. 使用任何 HTTP 伺服器運行
# 方法 1: Python
python -m http.server 8000

# 方法 2: Node.js (npx)
npx serve .

# 方法 3: 直接在瀏覽器開啟
# 雙擊 index.html 或右鍵 -> 以瀏覽器開啟
```

訪問 `http://localhost:8000` 開始使用

## 📐 系統架構

### 技術棧

- **前端框架**: React 18 (CDN)
- **UI 設計**: Tailwind CSS 3
- **圖示庫**: Lucide Icons
- **狀態管理**: React Context API
- **資料儲存**: LocalStorage (可擴展至後端 API)

### 專案結構

```
apqp-ppap-system/
├── index.html              # 主應用程式（單檔案 SPA）
├── README.md               # 專案說明文件
├── LICENSE                 # MIT 授權
├── .gitignore              # Git 忽略檔案
└── docs/                   # 文件目錄
    ├── screenshots/        # 系統截圖
    ├── user-guide.md       # 使用者手冊
    └── api-spec.md         # API 規格 (預留)
```

## 🎯 功能模組

### 1. Dashboard 專案總覽
- 專案卡片展示（進度環形圖）
- 即時統計（總數/進行中/已完成/逾期）
- 搜尋與篩選功能
- 快速進入專案詳情

### 2. 專案詳情頁

#### Tab 1: PSW 基本資料
- 零件名稱、編號、版次
- **零件淨重 (4位小數驗證)**
- 材料規格、製造地點
- 圖紙日期、提交等級
- 供應商/客戶簽名上傳
- 設備關聯選擇

#### Tab 2: APQP 五階段追蹤
| 階段 | 核心產出 |
|------|----------|
| 階段1 | 客戶特殊要求 (CSR)、初步風險評估、初步BOM |
| 階段2 | 可行性評估、模具設計圖、模具製作排程 |
| 階段3 | 製程流程圖 (PFD)、PFMEA、試產前控制計畫、SOP |
| 階段4 | MSA報告、初始製程能力 (Cpk)、FAI全尺寸報告 |
| 階段5 | 量產控制計畫、良率分析、經驗總結 (Lessons Learned) |

**關鍵特性**:
- ✅ 階段鎖定機制（前階段未審核則鎖定）
- ✅ 主管審核功能
- ✅ 部門權責控制

#### Tab 3: PPAP 18項查核
完整的 PPAP 提交要求清單：
1. 設計記錄
2. 工程更改文件
3. 客戶工程核准
4. 設計 FMEA
5. 製程流程圖
6. 製程 FMEA
7. 控制計畫
8. 量測系統分析 (MSA)
9. 全尺寸量測結果
10. 材料/性能測試報告
11. 初始製程能力 (Cpk)
12. 合格實驗室文件
13. 外觀批准報告 (AAR)
14. 零件樣品
15. 標準樣品
16. 檢查輔助具
17. 客戶特殊要求記錄
18. 零件提交保證書 (PSW)

#### Tab 4: 文件庫管理
- 拖曳上傳檔案
- 檔案預覽與下載
- 版本控制（預留）
- 支援格式: JPG, PNG, PDF

### 3. 權限系統

| 等級 | 角色 | 權限範圍 |
|------|------|----------|
| 00 | 管理員 | 完整系統權限、Log檢視 |
| 01 | 主管 | 審核、編輯、預覽、刪除 |
| 02 | 組員 | 編輯/刪除自己的檔案 |
| 03 | 訪客 | 僅供閱覽與進度查詢 |

### 4. CFT 部門權責

| 部門 | 主要負責項目 |
|------|-------------|
| **業務** | CSR、可行性評估、客戶協調、PSW簽回 |
| **工程** | BOM、流程圖、PFMEA、SOP、模具設計 |
| **品保** | 控制計畫、MSA/Cpk、FAI、客戶PPAP |
| **生產** | 試作與量產、SOP執行 |

## 🌐 多語系支援

- 🇹🇼 **繁體中文** (預設)
- 🇺🇸 **English**
- 🇹🇭 **ภาษาไทย**

所有介面、提示訊息、表單欄位均支援三語系切換

## 📊 資料結構

### 專案資料模型

```javascript
{
  id: 1,
  partName: "精密沖壓件A",
  partNumber: "P/N-12345678",
  revision: "Rev. 03",
  weight: "0.0245",  // 強制4位小數
  material: "SUS304",
  location: "精密沖壓 A 線",
  stage: 3,          // 當前階段 (1-5)
  progress: 65,      // 完成百分比
  status: "inProgress",
  equipment: ["200T沖床-A01", "OMM-M02"],
  apqpStages: [...], // APQP 五階段詳細資料
  ppapItems: [...]   // PPAP 18項詳細資料
}
```

## 🔧 未來擴展計畫

### Phase 4: 進階功能 (規劃中)
- [ ] 設備管理頁面
- [ ] 使用者管理 (CRUD)
- [ ] Email 自動通知
- [ ] 權限細粒度控制

### Phase 5: 雲端整合 (規劃中)
- [ ] 後端 API 串接
- [ ] 雲端檔案儲存 (AWS S3 / Azure Blob)
- [ ] Excel 報表自動匯出
- [ ] 數位簽核（時間戳 + IP記錄）
- [ ] 設備履歷追蹤

## 🤝 貢獻指南

歡迎貢獻！請遵循以下步驟：

1. Fork 本專案
2. 建立功能分支 (`git checkout -b feature/AmazingFeature`)
3. 提交變更 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 開啟 Pull Request

## 📝 授權協議

本專案採用 MIT 授權 - 詳見 [LICENSE](LICENSE) 檔案

## 👨‍💻 作者

**ayarfly-create**
- GitHub: [@ayarfly-create](https://github.com/ayarfly-create)
- Repository: [aqpq-ppap-system](https://github.com/ayarfly-create/aqpq-ppap-system)

## 🙏 致謝

- APQP 第三版標準參考
- AIAG-VDA FMEA 方法論
- 汽車業 PPAP 提交要求

## 📧 聯絡方式

如有問題或建議，請：
- 提交 [Issue](https://github.com/ayarfly-create/aqpq-ppap-system/issues)
- 訪問專案頁面：https://github.com/ayarfly-create/aqpq-ppap-system

---

**注意**: 本系統為前端原型，生產環境部署前請務必：
1. 實作後端 API 與資料庫
2. 加入使用者認證機制
3. 啟用 HTTPS 加密
4. 配置檔案上傳安全驗證
5. 實作完整的權限檢查邏輯
