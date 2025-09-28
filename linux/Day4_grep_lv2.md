#Day4 - 9/27 Linux & grep 練習 Notes (for nano)

[grep 常用指令]
grep "字串" 檔案        # 搜尋含有字串的行
grep -n "字串" 檔案      # 顯示行號
grep -i "字串" 檔案      # 忽略大小寫
grep -v "字串" 檔案      # 反向匹配 (顯示不含字串的行)
grep -E "A|B" 檔案       # 多條件 OR
grep "^字首" 檔案       # 找出以字首開頭的行
grep "字尾$" 檔案       # 找出以字尾結尾的行

[管線 (pipe |)]
- 把前一個指令的輸出，當作下一個指令的輸入
grep "a" words.txt | wc -l        # 找出含 a 的行數
cat words.txt | grep "oo"         # 找出含 oo 的行
grep "a" words.txt | sort | uniq  # 找出含 a 的單字，排序並去掉重複的

[wc (word count)]
wc -l  # 行數
wc -w  # 字數
wc -c  # 位元組數 (檔案大小)

[uniq]
- 移除相鄰的重複行
sort words.txt | uniq

[tr (translate)]
tr '[:lower:]' '[:upper:]'   # 小寫轉大寫
tr -d "a"                    # 刪掉所有字母 a
tr -s " "                    # 壓縮連續的空白為一個

[常見字元類別]
[:lower:]  小寫字母
[:upper:]  大寫字母
[:digit:]  數字
[:alpha:]  英文字母
[:alnum:]  英數字
[:space:]  空白字元

[小挑戰題目]
1. grep "a" words.txt | wc -l
2. grep "^b" words.txt | grep -v "a"
3. grep "a" words.txt | sort | uniq
4. grep "t$" words.txt | tr '[:lower:]' '[:upper:]'
