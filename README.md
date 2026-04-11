# Photo Classifier — Windows 桌面照片分類應用

> AI 驅動的本機照片管理工具：自動描述、智能標籤、人臉聚類、地點識別、語意搜尋。
> 完全離線運行（除 LLM API 呼叫外），照片資料不離開您的電腦。

## 下載

最新版本請至 [Releases 頁面](https://github.com/LUCAS88TSOI/photo-classifier-releases/releases) 下載：

| 安裝包 | 說明 |
|--------|------|
| `PhotoClassifier_x.y.z_x64-setup.exe` | NSIS 安裝程式（推薦，較小） |
| `PhotoClassifier_x.y.z_x64_en-US.msi` | MSI 安裝程式（適合 group policy 部署） |

**系統需求：**
- Windows 10 1809 或 Windows 11
- WebView2 Runtime（Win11 內建；Win10 [手動安裝](https://developer.microsoft.com/en-us/microsoft-edge/webview2/)）
- Python 3.10+（後端 FastAPI 服務）

## 主要功能

- 📸 **照片時間線** — 虛擬滾動，數十萬張照片流暢瀏覽
- 🤖 **AI 圖片描述** — 多供應商支援（Google Gemini / 智譜 / SiliconFlow / OpenAI 相容）
- 🏷️ **多維度標籤** — 人物 / 地點 / 場景 / 物件 / 自定義
- 👤 **人臉聚類** — InsightFace + DBSCAN，自動分組同一人物
- 🗺️ **GPS 地理編碼** — 反向解析地點名稱並生成地點標籤
- 🔍 **智能搜尋** — 文字 / 向量 / 標籤組合（AND/OR/NOT）混合查詢
- 💾 **METADATA 回寫** — 可選將 AI 結果寫入 EXIF/XMP，保留分類成果

## 快速開始

1. 下載並執行 `PhotoClassifier_x.y.z_x64-setup.exe`
2. 啟動後進入「設定」頁面，填入 LLM API Key（[Google AI Studio 免費取得](https://aistudio.google.com/apikey)）
3. 在「資料夾」頁面選擇要掃描的相片目錄
4. 等待 AI 處理管線完成後，即可在「時間線」/「標籤」/「探索」中瀏覽

## 技術棧

- **前端**：React 19 + TypeScript 5.8 + Vite 6 + Tailwind CSS 4 + Zustand 5
- **桌面框架**：Tauri 2.0 + WebView2
- **後端**：FastAPI + SQLite + LanceDB（向量資料庫）
- **AI**：Google Gemini（嵌入 + 視覺）+ InsightFace（人臉）

## 隱私與授權

- 照片資料只儲存在本機，不會上傳任何雲端
- 僅在執行 AI 描述/標籤時，**將縮圖**透過官方 API 傳送給您配置的 LLM 供應商
- 原始碼為私有倉庫，安裝包以 [LICENSE](LICENSE) 條款發佈

## 問題回報

[Issues 頁面](https://github.com/LUCAS88TSOI/photo-classifier-releases/issues) 歡迎回報 bug 與功能建議。
