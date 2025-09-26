# Day3 練習筆記
📅 日期：2025/09/26  
📝 主題：Linux 文字工具 & grep 基礎  
💡 狀態：精神普通（中午喝了小七榛果拿鐵，16:42 ~ 18:00 學習）

---

## 📂 版本1：上傳雲端用（Markdown / 純筆記版）
### Part A. 文字檢視工具
**cat**
- 一次輸出完整檔案。
- 適合小檔案。
```bash
cat sample.txt
```

**less**
- 可翻頁瀏覽（`space` 下翻，`b` 上翻）。
- 可搜尋（`/字串`，`n` 下一筆，`N` 上一筆）。
- 按 `q` 離開。
- 適合大檔案或 log。
```bash
less sample.txt
```

---

### Part B. grep 基礎
**單字搜尋**
```bash
grep "Wing" sample.txt
```

**區分大小寫（預設 ON）**
```bash
grep "dog" sample.txt   # 找不到
grep "DOG" sample.txt   # 找得到
```

**忽略大小寫**
```bash
grep -i "dog" sample.txt
```

**多關鍵字搜尋**
1. 多個 `-e`
   ```bash
   grep -e "apple" -e "Banana" sample.txt
   ```
2. 正則表示式
   ```bash
   grep -E "apple|Banana" sample.txt
   ```
3. 關鍵字檔案
   ```bash
   grep -f keywords.txt sample.txt
   ```

---

### Part C. Here Document (Heredoc)
**基本語法**
```bash
cat << EOF
Hello Wing
EOF
```
- `EOF` 可換成任意字（CASE/END/DATA）。
- `<< "EOF"` → 不展開變數。
- `<< EOF` → 會展開變數。

**輸出到檔案**
```bash
cat > sample.txt << EOF
My name is $USER
EOF
```
- `>`：覆蓋檔案。
- `>>`：追加到檔案尾端。

---

### 今日小結
- 熟悉了 `cat` 與 `less` 差異。  
- 學會 `grep` 搜尋大小寫、多字詞。  
- 理解 Here Document 與 `>` / `>>` 重定向的差別。  
- 生成了中型 `sample.txt`（40 行）作為練習資料。  

✅ 今日進度完成！下一步：管線 `|` 與進階 grep。

---

## 🗒️ 版本2：Notion 留存用（簡潔清單）
### Day3 筆記（2025/09/26）
- 主題：Linux 文字工具 & grep
- cat：快速顯示小檔案
- less：可翻頁、搜尋 (`/字串`)，大檔案適用
- grep：
  - 預設區分大小寫
  - `-i` 忽略大小寫
  - `-e` 多關鍵字
  - `-E "a|b"` 正則 OR
  - `-f` 從檔案讀關鍵字
- Here Document：
  - `<< EOF ... EOF` → 多行輸入
  - `<< "EOF"` → 不展開變數
  - `>` 覆蓋；`>>` 追加
- 今日重點：  
  熟悉文字檢視工具、grep 基本用法、Heredoc 與重定向差異
