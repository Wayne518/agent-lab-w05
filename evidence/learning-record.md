# My lab evidence / 我的實作紀錄

Use a group code, not real names or student IDs in shared files. / 共用檔只寫組別代碼，不寫姓名或學號。

- Group code / 組別：NDHU-W05
- Tool / 工具：Antigravity (with Gemini & Git CLI)
- Route / 路線：individual 個人
- Tasks completed / 完成題目：A, B, C, D
- Material / 素材：NDHU classroom tasks 東華課堂版
- For original-pack work: task number, author/source link and version / 原版實作：題號、作者來源連結與版本：東華課堂版（無原版題號）
- My role and what I checked / 我的角色與實際檢查：操作與驗收。檢查了 A 題檔案雜湊一致性與版本保留、B 題 6 項過濾測試與快捷鍵功能、C 題空列移除與欄位衝突、D 題審查模擬計畫並提出退回要求。

## Scope and plan / 範圍與計畫

Allowed input and output folders / 可讀取與輸出的資料夾：
- 任務 A：`practice/01-club-files/input` -> `practice/01-club-files/output`
- 任務 B：`practice/02-campus-picker/activities.json` -> `practice/02-campus-picker/output/index.html`
- 任務 C：`practice/03-equipment/equipment.json` -> `practice/03-equipment/output`
- 任務 D：`practice/04-review/bad-plan.txt` -> `practice/04-review/my-rejection.md`

What I asked for / 原始需求：
- A：整理 12 個社團檔案，原檔不動，保留副本與版本差異，輸出 manifest.json 與 report.md。
- B：單頁離線活動挑選器，支援地點、時間、強度三條件隨機篩選、5 筆歷史紀錄、重設篩選、中英文切換。
- C：清理 10 筆器材資料，去空格、狀態正規化、保留空值負數原樣、列出衝突。
- D：退回不合理的下載目錄大掃除計畫。

What I checked before execution / 動手前我檢查了什麼：
檢查 Agent 提出的計畫中，是否明確承諾「只處理指定的 input 資料夾」、「原檔案不刪除、不覆蓋」、「不連外、不安裝額外套件」。確認計畫無破壞性動作後才給予「執行」指令。

## Tests actually performed / 我真的做過的測試

| Test / 測試 | Expected / 預期 | Observed / 實際 | Evidence / 證據 |
|---|---|---|---|
| 1. Task A 檔案完整性與副本檢查 | 12 個原檔雜湊與 output 副本 100% 相同；final 與 final2 兩版本均保留 | SHA-256 逐一比對完全吻合；proposal_final.txt 與 proposal_final2.txt 均存在於 output/proposals/ | manifest.json 陣列 12 筆，雜湊比對腳本通過 |
| 2. Task B 室外/15分鐘/中強度篩選 | 顯示「沒有符合條件的活動」，不放寬條件 | 頁面呈現紅框文字「沒有符合條件的活動」，歷史紀錄未增加 | 瀏覽器實際操作驗收 |
| 3. Task B 鍵盤快捷鍵 (B v2) | 按 Space/Enter 抽選，按 R 重設 | 畫面立即抽中活動並更新歷史，按 R 重設為不限/30/不限 | index.html 鍵盤監聽事件與 UI 提示徽章 |

## One revision / 一次修改

Before / 原來的情況：
活動挑選器僅能用滑鼠點擊按鈕操作，在電腦端操作不夠直覺迅速。

Request / 我提出的修改：
支援鍵盤快捷鍵（`Space` / `Enter` 觸發「幫我選」、`R` 鍵觸發「重設篩選」），並在按鈕與介面新增快捷提示徽章，支援雙語。

After and retest / 修改後與重測結果：
在頁面上隨意按空白鍵或 Enter 即可流暢抽籤，按 R 可即時重設篩選條件，中英文介面切換時快捷文字皆正確顯示。

New requirement or defect? / 新需求還是原規格未做到？：
新需求（使用者操作體驗強化）。

## One rejection / 一次退回

Which action I reject and why / 退回哪個動作、為什麼：
退回「整理整個 Downloads 資料夾、刪除重複檔、把 final2 當最新版、找不到資料就補合理值、自動公開成果」。
理由：未經授權擴大操作範圍有洩漏私密與破壞檔案風險；刪除原檔具不可逆危險；以檔名認定最新版會誤失不同活動方案；偽造數據掩蓋缺失；自動公開成果會引發資安與未審核內容外洩風險。

An acceptable alternative / 可以怎麼改：
嚴格限縮工作目錄在指定資料夾；保持原檔只讀並於 output 輸出副本；完整保留所有企畫版本並建立差異報告；缺失資料原樣保留並列入問題清單；成果只留本機 output，待人工驗核完成後才手動發布。

## Still unverified / 還沒驗證

What I cannot claim is complete / 哪些事不能說已完成：
1. 社團活動企畫案最終採納室內還是室外方案，仍待幹部會議決策。
2. 模擬器材資料中缺少的膠帶數量與紙張包數量，仍需人工進行實體倉庫盤點才能確定。
3. 活動挑選器的隨機演算法在統計學上的長期機率均勻性尚未經大量次數（如上萬次）卡方檢定驗證。

For the fallback route, mark all prepared evidence as supplied simulation. / 備援路線請標明所有預生成證據來源，不能填成自己的Agent實跑。
（本實作全程由本機 Agent 與 Git 實跑驗證，非備援路線）
