---
name: data-analyst
description: 輕量級資料分析師核心技能包。內建專業分析師思考框架、標準 Prompt 提示詞樣板、自動化資料清洗腳本（處理逗號千分位、百分比、空白修剪與缺失值）與資料前處理速查表。
license: MIT
metadata:
  version: "1.0.0"
  author: "nutcelvischen-jpg"
---

# 資料分析師技能包 (Data Analyst Skill)

本技能專為資料分析師、學員與 AI Agent 設計，提供從「原始髒資料 ➔ 自動化清洗 ➔ 探索性分析 (EDA) ➔ 商業決策洞察」的標準化作業能力。

---

## 1. 核心組成與目錄結構

```
data-analyst/
├── SKILL.md                          # 技能主說明與 4 大標準 Prompt 提示詞樣板
├── README.md                         # 專案快速上手指南
├── scripts/
│   └── clean_data.py                 # 自動化資料清洗腳本 (標準化數值/百分比/缺失值)
└── references/
    ├── cleaning_rules.md             # 資料清洗常見 5 大陷阱與 Pandas 速查表
    └── sample_dirty_data.csv         # 練手用髒資料範例檔
```

---

## 2. 四大標準資料分析師 Prompt 提示詞樣板

學員或 AI Agent 在進行資料分析時，可直接引用以下經實戰驗證的 Prompt 樣板：

### 📋 Prompt 樣板 1：商業需求界定與欄位拆解
> 「你現在是一位資深商業資料分析師。我想要探討【分析主題，例如：日本高齡化對地方房價與所得的影響】。  
> 請幫我進行以下拆解：  
> 1. **核心度量 (Measures/數值)**：我們需要計算或比較哪些關鍵數字？（例如：高齡化率%、平均所得、空屋率）  
> 2. **核心維度 (Dimensions/分類)**：我們需要按什麼視角切分？（例如：都道府縣、地方分區、年份）  
> 3. **圖表選型建議**：依據變數型態（離散/連續/時序/地理），建議使用哪種視覺化圖表最適合向主管報告？」

### 🧹 Prompt 樣板 2：資料品質檢查與清洗指引
> 「這是一份剛從外部資料庫或 API 匯出的原始資料。請幫我依據 `cleaning_rules.md` 進行資料體檢：  
> 1. 是否有帶千分位逗號的數字字串（例如 `"1,234,000"`）需要轉換？  
> 2. 是否有百分比符號 `%` 阻礙了數值運算？  
> 3. 是否存在空白列、`null`、`NaN` 或極端異常值？  
> 請直接調用 `scripts/clean_data.py` 進行標準化清洗，並回報清洗摘要統計。」

### 🔍 Prompt 樣板 3：探索性數據分析 (EDA)
> 「資料已清洗完成，請幫我針對關鍵度量進行初步探索分析：  
> 1. 提供基本描述性統計（平均數、中位數、最大/最小值、標準差）。  
> 2. 找出排行前 3 名與後 3 名的極端案例，並分析其背後可能的特徵。  
> 3. 檢查兩個變數之間的相關性（正相關/負相關/離群點），並說明這對商業決策意味著什麼。」

### 💡 Prompt 樣板 4：三段論商業洞察與決策報告
> 「請根據我們產出的視覺化圖表，撰寫一份簡潔有力的 C-Level 主管匯報結論，遵循以下三段結構：  
> 1. **現況事實 (What is happening)**：用 2 句話與精確數字總結數據呈現的核心現象。  
> 2. **深度原因 (Why it matters)**：結合產業背景或結構趨勢，解釋為何會出現此現象。  
> 3. **行動建議 (What should we do)**：給出 2 項具體、可落地的行動建議或下一步分析方向。」

---

## 3. 資料清洗腳本使用方式

本技能內建獨立純 Python 腳本（無額外複雜依賴）：

```bash
# 基本語法
python3 scripts/clean_data.py <輸入檔案.csv> [輸出檔案.csv]

# 範例：清洗練手用髒資料
python3 scripts/clean_data.py references/sample_dirty_data.csv cleaned_data.csv
```

### 腳本執行成果範例：
```
============================================================
✓ 資料清洗作業完成！ (Data Analyst Skill)
• 原始檔案: references/sample_dirty_data.csv (編碼: utf-8)
• 清洗產出: cleaned_data.csv
• 處理欄數: 6 欄
• 有效列數: 6 列
• 標準化數值/百分比: 15 個欄位
• 空白缺失欄位記錄: 1 處
============================================================
```

---

## 4. 參考文件

* 詳細清洗規則與常用 Pandas 語法：[references/cleaning_rules.md](references/cleaning_rules.md)
* 測試用範例資料：[references/sample_dirty_data.csv](references/sample_dirty_data.csv)
