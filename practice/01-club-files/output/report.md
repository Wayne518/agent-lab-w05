# 社團檔案整理報告 (Club Files Organization Report)

## 一、整理摘要
- **原始檔案來源**：`input/`（共 12 個檔案）
- **整理後輸出目錄**：`output/`（共 12 個檔案副本，原檔完整未動）
- **分類目錄**：
  - `proposals/`：4 個檔案
  - `admin/`：4 個檔案
  - `publicity/`：4 個檔案
- **完整性檢驗**：所有檔案之 SHA-256 雜湊值均與原始檔案 100% 比對一致，無任何修改、覆蓋或遺失。

---

## 二、分類架構與說明

### 1. `proposals/`（企畫與活動方案）
收錄活動發想、提案版本、備案與後續討論方向：
- `proposal_final.txt`：戶外活動企畫第一版（30分鐘）。
- `proposal_final2.txt`：室內活動企畫第二版（20分鐘）。
- `rain_plan.txt`：雨備方案（若遇下雨另議室內方案）。
- `next_steps.txt`：企畫後續事項提示（提醒兩者皆尚未定案，需進行比較）。

### 2. `admin/`（行政、財務與物資）
收錄預算草案、器材物資盤點與會議紀錄：
- `budget_draft.txt`：紙張預算草案（模擬值 100，尚未核定）。
- `equipment_list.txt`：活動器材清單（簽字筆 4、紙 2 包）。
- `equipment_backup.txt`：器材清單副本（內容與 `equipment_list.txt` 完全相同）。
- `meeting_notes.txt`：會議紀錄（下次會議將決定室內或室外方案）。

### 3. `publicity/`（宣傳推廣與問卷）
收錄宣傳公告、海報文案與回饋調查題目：
- `announcement.txt`：活動公告（提醒自備筆記本，時間地點待定）。
- `announcement_copy.txt`：活動公告副本（內容與 `announcement.txt` 完全相同）。
- `poster_text.txt`：宣傳海報簡短文案。
- `feedback_questions.txt`：活動回饋問卷規劃問題。

---

## 三、重複檔案與多版本比對分析

### 1. 內容完全重複之檔案（SHA-256 一致）
- **`announcement.txt` 與 `announcement_copy.txt`**
  - SHA-256: `C19164B1054EBF52ED33BC5321C887985EA043A0B07DB1E99F866986D2CCD584`
  - 處理方式：兩者內容完全相同，依規範各自保留完整副本於 `publicity/`，不進行刪除或合併。
- **`equipment_list.txt` 與 `equipment_backup.txt`**
  - SHA-256: `C21D53BA1F8D3AD06E1833539935120A5BACA4D13B34A2AA98CE157FF4502FA3`
  - 處理方式：兩者內容完全相同，依規範各自保留完整副本於 `admin/`，不進行刪除或合併。

### 2. 名稱相近但內容不同之版本
- **`proposal_final.txt` vs `proposal_final2.txt`**
  - `proposal_final.txt` 內容：「企畫第一版：戶外活動，30分鐘。尚未定案。」
  - `proposal_final2.txt` 內容：「企畫第二版：室內活動，20分鐘。仍待討論。」
  - 判定：雖然檔名均包含「final」，但內容為完全不同的兩種活動企畫方案（戶外 30 分鐘 vs 室內 20 分鐘），且文件內文明確標註「尚未定案」與「仍待討論」。因此絕不能僅以檔名中的 final 或檔案修改時間認定誰是定稿，兩個版本均完整保留於 `proposals/` 供團隊決策。

---

## 四、待確認問題與後續建議（待人工作業）
1. **企畫方案定案**：團隊需於下次會議比對 `proposal_final.txt`（戶外）與 `proposal_final2.txt`（室內），並搭配 `rain_plan.txt` 確認最終定稿方案。
2. **預算審核**：`budget_draft.txt` 中所列之紙張預算為模擬值 100，仍待社團幹部核定。
3. **時間地點確認**：`announcement.txt` 提及時間地點尚未決定，待企畫定案後需更新正式公告內容。
4. **重複備份清理決策**：`announcement_copy.txt` 及 `equipment_backup.txt` 現已完整備份保留，未來若需精簡目錄架構，可由負責人人工確認後再評估是否歸檔或移除重複檔。
