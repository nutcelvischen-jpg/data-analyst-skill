# Data Analyst Skill (輕量級資料分析師技能包)

專為資料分析初學者、學員與 AI Agent 設計的輕量標準化技能。包含：
- 4 大標準資料分析師 Prompt 提示詞樣板（需求拆解、資料體檢、EDA 探索、三段論報告）
- 自動化資料清洗腳本 (`scripts/clean_data.py`)
- 資料前處理速查表與範例資料集 (`references/`)

## 快速開始

### 1. 執行資料清洗腳本
```bash
python3 scripts/clean_data.py references/sample_dirty_data.csv cleaned_data.csv
```

### 2. 在 Antigravity 或 Agent 中使用
Agent 會自動讀取 `SKILL.md` 中的 4 大提示詞框架，並依據標準作業程序（SOP）引導學員完成數據前處理與洞察報告。

## 授權
MIT License
