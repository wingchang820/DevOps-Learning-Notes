Day5 (9/28) 學習重點 – Git 衝突與 Rebase

今日流程
1. 建立分支 feature-a 和 feature-b
   git switch -c feature-a
   git switch main
   git switch -c feature-b

2. 在兩個分支修改 story.txt 同一行，製造衝突

3. 使用 git diff feature-a..feature-b 檢查差異
   - This line from feature A
   + This line from feature B
   代表同一行被修改，必定衝突

4. 嘗試合併 git merge，會出現衝突，需要手動解決
   如果沒處理衝突，Git 會顯示 "unmerged files"

5. 使用 git rebase feature-a
   rebase 途中遇到衝突，Git 停下來
   解決檔案 → git add story.txt → git rebase --continue
   進入編輯器確認 commit 訊息後存檔
   完成後 feature-b 歷史接在 feature-a 後面，形成線性歷史

------------------------------------------------------------

Q&A 紀錄
1. git checkout vs git switch
   checkout = 舊用法，功能多但容易混淆
   switch = 新用法，專門切換或建立分支
   建議：練習用 switch，但要懂 checkout

2. -b vs -c
   git switch -b feature-a
   git switch -c feature-a
   效果相同，都是建立並切換新分支

3. git commit -am
   -a = 自動 add 已追蹤檔案
   -m = commit 訊息
   適合修改舊檔，不包含新檔案

4. 如何檢查分支衝突
   git diff branchA..branchB
   如果同一區塊同時有 - 和 +，代表有潛在衝突

5. 為什麼 rebase 要 --continue
   rebase 衝突時 Git 會停住
   --continue = 告訴 Git 已解決，繼續進行
   如果沒下，Git 會卡在 rebase 狀態

6. 衝突處理的三條路
   git add <file> + git rebase --continue   (繼續)
   git rebase --skip                        (跳過這筆 commit)
   git rebase --abort                       (放棄 rebase)

------------------------------------------------------------

小抄
git diff A..B                檢查分支差異
git merge branch             合併分支
git merge --abort            放棄合併
git rebase branch            把目前分支接到另一分支後面
git rebase --continue        繼續 rebase
git rebase --skip            跳過這筆 commit
git rebase --abort           中止 rebase
git status                   檢查衝突狀態
git add <file>               標記衝突已解決
git log --oneline --graph -N 查看歷史與分支走向
