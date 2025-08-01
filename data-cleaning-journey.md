# SQL Data Cleaning Journey: A Real-World Simulation

This project simulates a real-world data cleaning process using SQL and DB Browser for SQLite. It documents how raw, messy data was cleaned step-by-step and prepared for visualization in Power BI — including all the logic, lessons, and challenges encountered along the way.

## About This Project

This project is a hands-on simulation of a real data cleaning workflow. The primary aim was to:

- Start from scratch with a messy `.db` file.
- Clean and transform fields like Email, Subscription_Type, and Last_Login.
- Document each step in SQL.
- Connect and analyze the cleaned data using Power BI.
- Reflect on the full journey as a LinkedIn post.

## Project Goals

- Inspect the Schema: Understand column names and data types before cleaning.
- Clean Messy Fields: Standardize email, fix date formats, and validate subscription values.
- Write Reusable SQL: Use clear and readable queries with comments.
- Save and Document the Process: Make it GitHub-friendly.
- Reflect and Share: Turn the journey into personal branding content.

## Step-by-Step Process I Followed

### Schema Inspection

- Used `PRAGMA table_info(MOCK_DATA);` to review columns and data types.

### Step 1: Email Cleaning

- Removed special characters and whitespace.
- Replaced empty or NULLs with `unknown@email.com`.
- Validated using `LIKE '%@%.%'`.

### Step 2: Subscription_Type Cleaning

- Removed leading/trailing spaces and special symbols.
- Normalized case to Title Case (e.g., basic → Basic).
- Removed invalid or empty plan types.

### Step 3: Last_Login Date Cleaning

- Faced formats like 05/02/2025, 5-05-05-2025, 29-09-2024.
- Standardized all to YYYY-MM-DD using `substr`, `length`, and `printf`.
- Carefully used `LIKE` to target only messy formats (e.g., `WHERE Last_Login LIKE '_-__-__-____'`).
- Removed unrealistic dates like 0-01-10-2025 after identifying them.

### Validation

- Verified results after each step with `SELECT DISTINCT` and `LIKE` filters.
- Ensured Last_Login has only YYYY-MM-DD formats at the end.

### Saved All SQL Queries

- In a clean, GitHub-friendly markdown format with comments using `--` style.

## Challenges Faced

- `instr()` gave errors due to wrong arguments.
- Date cleaning logic needed simplification.
- Missed edge cases like 0-prefixes in day/month values.
- Emails that looked strange but were still valid — had to make judgment calls.

## Lessons I Learned

- Always understand your data patterns first.
- Test using `SELECT` before doing `UPDATE`.
- Use string functions like `substr`, `printf`, and `length` smartly.
- Don’t assume — validate everything.

## Power BI Cleaning Journey

### Step 1 – First Attempt with DB File

- Exported the cleaned SQL data as a .db file.
- Installed DLL drivers and tried to connect Power BI with ODBC.
- Faced multiple compatibility issues:
  - 32-bit vs 64-bit drivers
  - Installing/uninstalling different ODBC versions
- Even after connection, Power BI table view showed repeated values in some columns.
- Lesson: Connecting through ODBC is tricky and not always stable for small projects.

### Step 2 – Switching to Excel / CSV Import

- Converted the DB file to Excel/CSV out of frustration.
- Imported into Power BI again, but the same “repeated values” issue appeared.
- Spent hours trying to figure out if the dataset was broken — only to later discover:
  - Power BI groups values in Data View; it wasn’t a real data problem.
- Lesson: Don’t trust the Table View blindly — always confirm with distinct counts or visuals.

### Step 3 – Power Query Cleaning Battles

- Opened Power Query Editor.
- Discovered auto-added steps like Changed Type, Changed Type with Locale, and Keep Errors.
- Mistakenly used Keep Errors — dataset collapsed to only a few rows.
- Deleted steps, retried with Replace Errors — null instead.
- Handled messy dates (e.g., 2024-02-30) by replacing them with nulls.
- Final Last_Login column: 99% valid, less than 1% null.
- Lesson: Replace > Remove — never wipe rows unless they’re truly unusable.

### Step 4 – Row Reduction (1000+ → 657)

- Email column had invalid addresses and blanks.
- Many rows had nulls in critical fields — dropped them carefully.
- Final dataset reduced from over 1000 to 657 rows, but every row is valid and reliable.
- Lesson: Row reduction is not random — it’s about improving quality, not shrinking size.

### Step 5 – Final Realization

- Subscription_Type and Dropped_Off weren’t broken.
- Power BI Table View was simply showing all Premium rows first, then Basic, then Free.
- Same with Dropped_Off (False first, then True).
- Lesson: What looks like a problem might just be Power BI’s display logic.

## Strong Lessons From This Journey

- Installing drivers, ODBC, DLLs is valuable but time-consuming. Start simpler next time.
- Always question the view versus the real data.
- Keep Power Query steps minimal to avoid freezing.
- Save work frequently — progress can be lost due to freezes.
- Real datasets are messy — nulls, invalids, and errors are normal. Handling them builds confidence.
- Quality is better than quantity — 657 reliable rows are more valuable than 1000 messy ones.

## Final Outcome

- Clean dataset: 657 rows of high quality.
- Last_Login column fixed with 99% valid entries.
- Subscription types preserved: Free, Basic, Premium.
- Drop-offs preserved: TRUE/FALSE.
- Dataset now ready for EDA and dashboard building.

## Contact

- LinkedIn: https://www.linkedin.com/in/ajayprasanth1
- Email: ajayprasanth2026@gmail.com
