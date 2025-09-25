# DevOps Learning Notes

這是我的 DevOps 學習筆記，紀錄從零開始到逐步熟悉 Linux、Git、Python、CI/CD、
雲端自動化的過程。每一天的練習都像遊戲存檔，方便自己回顧，也能當成作品展示。

## 🎯 學習目標
- 打好 Linux & Git 基礎
- 熟悉 Python 自動化
- 逐步理解 CI/CD 與 Kubernetes
- 建立屬於自己的 DevOps 技能樹

## 📂 筆記結構

	DevOps-Learning-Notes/
	├── README.md # 專案簡介
	├── linux/ # Linux 練習筆記
	├── git/ # Git 練習筆記
	├── python/ # Python 練習筆記
	└── misc/ # 其他資源


## 📅 每日紀錄方式
- 每個主題按「DayX」切分檔案，例如 `linux/Day1_basic.md`  
- 紀錄包含：
  - 今日目標
  - 實際操作（指令 & 結果）
  - 心得/小提醒

## 🚀 使用方式
1. Clone 專案

   git clone https://github.com/wingchang820/DevOps-Learning-Notes.git

## ⚡ 2. 每天整理後 push 到 GitHub 的流程

假設妳已經在本機有 `DevOps-Learning-Notes` 這個資料夾，並且跟 GitHub 建立過 repo 連線。  
以下是每天的固定流程（我幫妳寫成「日常存檔儀式」）：  

---

### 🕹️ Step 1：更新筆記

- 在 `linux/DayX_xxx.md` 或其他目錄補上今天的內容。

---

### 🕹️ Step 2：查看變更

git status

---
###   Step 3：把修改加入暫存區

git add .

（. 代表所有有變更的檔案。如果想只加特定檔案，可以改成 git add 檔名）

---
###   Step 4：建立 commit

git commit -m "Day2: 路徑與通配符練習筆記"

👉 記錄今天的內容，訊息用「DayX: 主題」會很清楚。

###  Step 5：推送到 GitHub

git push origin main


（如果妳的分支不是 main，可能是 master，就改成 git push origin master）

###🕹️ Step 6：（可選）確認 GitHub 上是否更新

打開 GitHub repo 頁面，看筆記是否出現在雲端。

