# ✅ SQL Data Cleaning Project Journey

## 🎯 Goal
Simulate a real-world data cleaning project using **SQL** and **DB Browser for SQLite** — from raw data to a clean, analysis-ready dataset, and reflect on the technical and mental lessons learned.

---

## 🧱 Step-by-Step SQL Cleaning Process

### 🔍 Schema Inspection
- Used `PRAGMA table_info(MOCK_DATA);` to review table structure, columns, and data types.

### 📧 Step 1: Email Cleaning
- Removed special characters and whitespace using `REPLACE`, `TRIM`, etc.
- Replaced empty or NULL emails with a placeholder: `unknown@email.com`.
- Validated format using `LIKE '%@%.%'`.

### 💼 Step 2: Subscription_Type Cleaning
- Removed leading/trailing spaces and special characters.
- Normalized to Title Case (`basic` → `Basic`, etc.).
- Removed invalid or empty subscription types.

### 🕓 Step 3: Last_Login Date Cleaning
- Faced formats like `05/02/2025`, `5-05-05-2025`, `29-09-2024`.
- Standardized to `YYYY-MM-DD` using `substr()`, `length()`, and `printf()`.
- Targeted formats carefully using `LIKE '_-__-__-____'`.
- Removed unrealistic entries like `0-01-10-2025`.

### 🔎 Validation
- Used `SELECT DISTINCT` to verify results.
- Ensured `Last_Login` has only `YYYY-MM-DD` values.

### 💾 Final SQL
- Saved all queries in GitHub-friendly `.sql` file format with inline comments (`--` style).

---

## ⚠️ Challenges Faced
- `instr()` errors due to wrong usage.
- Date logic required simplification.
- Missed edge cases like `0`-prefixed dates.
- Some strange-looking emails were technically valid — required judgment calls.

---

## 🧠 Lessons Learned
- Always understand your data patterns before cleaning.
- Test changes using `SELECT` before running `UPDATE`.
- Use string functions (`substr`, `printf`, `length`) wisely.
- Never assume — validate everything.

---

# 📘 Power BI + Data Quality Battles

## 🔹 Step 1 – Connecting DB with Power BI (ODBC)
- Exported cleaned `.db` file.
- Installed DLLs and tried 32-bit/64-bit ODBC drivers.
- Faced repeated values in Power BI's Table View.
- **Lesson:** ODBC isn't always stable for small projects.

## 🔹 Step 2 – Switching to Excel/CSV Import
- Converted `.db` to `.csv` for import.
- Same repeated value issue appeared.
- Later discovered Power BI **groups** values in Table View.
- **Lesson:** Always verify with `DISTINCT`, not just visual appearance.

## 🔹 Step 3 – Power Query Cleaning
- Mistakenly used `Keep Errors` → most data vanished.
- Replaced errors instead of removing rows.
- Cleaned dates like `2024-02-30` to `NULL`.
- Final cleaned `Last_Login` → 99% valid.
- **Lesson:** Replace > Remove. Keep rows unless truly unusable.

## 🔹 Step 4 – Row Reduction (1000+ → 657)
- Dropped rows with critical nulls after careful review.
- **Lesson:** Reducing rows is about improving quality, not just cutting size.

## 🔹 Step 5 – Realizing False Alarms
- Subscription types and drop-off values were not broken.
- Power BI Table View **sorts** values visually.
- **Lesson:** Trust logic, not just what the screen shows.

---

## 🚀 Final Outcome

| Metric                     | Result            |
|---------------------------|-------------------|
| Initial Rows              | ~1000             |
| Final Rows                | 657               |
| Valid Email Addresses     | ✅ Cleaned         |
| Last_Login Dates          | ✅ 99% Valid       |
| Subscription_Type         | ✅ Free, Basic, Premium |
| Dropped_Off Values        | ✅ TRUE / FALSE    |

---

## 🧠 Strong Takeaways
- Real-world datasets are always messy — learn to handle uncertainty.
- String/date cleaning builds deep SQL confidence.
- Visual tools (like Power BI) may mislead — always double-check your logic.
- Use versioning and save often — freezes are real.
- Quality > Quantity: 657 clean rows > 1000+ messy ones.
- This was not just cleaning — it was a battle with tools, errors, and mindset.

---

## 🔗 Next Steps
- Begin Exploratory Data Analysis (EDA).
- Build a dashboard with insights from the cleaned dataset.
- Use this project as a learning artifact for resumes and LinkedIn.

---

## 🙌 Author: Ajay Prasanth
_Thanks for reading my SQL + Power BI Data Cleaning Journey._

If you found this helpful, feel free to connect with me on [LinkedIn](https://www.linkedin.com).