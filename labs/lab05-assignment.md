# Lab Assignment 5: Cleaning and Resolving Data Issues

**CAP2791C: Power BI Data Preparation and Modeling**  
**Miami Dade College | Business Intelligence Certification**

---

## Assignment Overview

| | |
|---|---|
| **Chapter** | Chapter 5 — Cleaning and Resolving Data Issues |
| **Competencies** | C3.1, C3.2, C3.7, C3.9 \| PL-300: Clean |
| **Tool** | Power BI Desktop → Power Query Editor |
| **File to open** | Your Sabor Miami .pbix file (with all 5 tables connected from Chapters 2–3) |
| **Time estimate** | 30–45 minutes |
| **Points** | 100 points |
| **What you will submit** | Your cleaned .pbix file + a short written response (see Submission Instructions) |

---

## What You Are Doing

In Chapter 4, you profiled all five Sabor Miami tables and documented at least 10 data quality issues. In this assignment, you will **fix those issues** using the cleaning techniques from Chapter 5. By the end, your dataset should have no unresolved errors, consistent text values, correct data types, and clear column and query names.

This assignment mirrors the Practice Exercise from the chapter. If you get stuck on a task, refer back to the Chapter 5 walkthrough for step-by-step guidance.

---

## Grading Rubric

Grading criteria are provided upfront so you know exactly what to aim for.

| Task | Points | What I Am Looking For |
|------|--------|-----------------------|
| **Task 1:** Resolve null values | 15 pts | Null tips replaced with 0 in Sales. Null phone numbers left as null in Employees. Applied Steps reflect both decisions. |
| **Task 2:** Fix text inconsistencies | 20 pts | Menu Items categories standardized (no duplicate variants). Employee names in Proper Case. Truck name typo corrected. Trailing spaces trimmed. |
| **Task 3:** Standardize values | 10 pts | Payment methods use consistent casing. No duplicate variants visible in Column Distribution. |
| **Task 4:** Resolve data type errors | 20 pts | Dollar signs removed from Menu Items Price column. Price column data type is Decimal Number (not Text). No errors in the column. Correct order of operations used (clean text first, then change type). |
| **Task 5:** Apply naming conventions | 15 pts | All columns use spaces instead of underscores. All five queries renamed to clean names (Sales, Menu Items, Trucks, Employees, Events). |
| **Task 6:** Verify and reflect | 20 pts | Column Quality shows 100% Valid (or near-100% with justified nulls). Written response answers both questions thoughtfully (2–3 sentences each). |
| **TOTAL** | **100 pts** | |

---

## Before You Begin

<div style="background-color: #1a1a2e; border: 2px solid #16a085; padding: 20px; margin: 15px 0; border-radius: 8px;">
  <strong style="color: #16a085; font-size: 1.1em;">🚀 LAUNCH PAD</strong><br><br>
  <strong>What you are building:</strong> A fully cleaned version of the Sabor Miami dataset<br>
  <strong>Tool:</strong> Power BI Desktop → Power Query Editor<br>
  <strong>File to open:</strong> Your .pbix file with all 5 Sabor Miami tables (from Chapters 2–3)<br>
  <strong>Data source:</strong> All 5 Sabor Miami files (Sales, Menu Items, Trucks, Employees, Events)<br>
  <strong>Time estimate:</strong> 30–45 minutes<br>
  <strong>Number of tasks:</strong> 6<br>
  <strong>What "done" looks like:</strong> All 5 tables cleaned — no errors, consistent text, correct data types, clear names, and a short written response<br>
  <strong>Start here →</strong> Open your .pbix file and click Transform Data on the Home tab
</div>

> **WHERE AM I?** All tasks in this assignment take place in the **Power Query Editor** (the separate window with the green ribbon). If you see the main Power BI canvas, click **Transform Data** on the Home tab to open the Power Query Editor.

---

## Tasks

### Task 1: Resolve Null Values (15 points)

**Sales table:**

1. Click the **Sales** query in the Queries pane.
2. Select the **Tip** column.
3. Replace null values with **0** using Replace Values.

**Employees table:**

4. Click the **Employees** query in the Queries pane.
5. Check for null values in the phone number column. **Do not replace these.** Leave them as null — a missing phone number does not mean the number is zero.

<div style="background-color: #FADBD8; border-left: 5px solid #E74C3C; padding: 15px; margin: 15px 0; border-radius: 4px;">
  <strong style="color: #922B21;">🛑 STOP AND CHECK</strong><br>
  In the Sales table, scroll through the Tip column. You should see 0 where nulls used to be. The Applied Steps pane should show a new step called "Replaced Value."<br><br>
  In the Employees table, null phone numbers should still appear as null — no changes made.
</div>

---

### Task 2: Fix Text Inconsistencies (20 points)

**Menu Items table:**

1. Select the **Category** column.
2. Use Replace Values to standardize all variants of "Entrée" (fix "Entree" and "entree" to "Entrée").

**Employees table:**

3. Select the **First_Name** column. Apply **Proper Case** (Transform tab → Format → Capitalize Each Word).
4. Repeat for the **Last_Name** column.
5. Apply **Trim** to both name columns to remove trailing spaces (Transform tab → Format → Trim).

**Trucks table:**

6. Use Replace Values to fix "Kendal" → "Kendall."

<div style="background-color: #FADBD8; border-left: 5px solid #E74C3C; padding: 15px; margin: 15px 0; border-radius: 4px;">
  <strong style="color: #922B21;">🛑 STOP AND CHECK</strong><br>
  Turn on Column Distribution (View tab → Data Preview section → Column Distribution) for the Category column in Menu Items. The number of distinct values should match the number of actual categories — no duplicates caused by casing or spelling.<br><br>
  In the Employees table, all names should be in consistent format (e.g., "Maria Garcia," not "MARIA GARCIA" or "maria garcia").
</div>

---

### Task 3: Standardize Values (10 points)

**Sales table:**

1. Select the payment method column.
2. Use Replace Values to standardize all casing variants to one consistent form (e.g., "CASH" → "Cash," "cash" → "Cash").
3. If credit card variants exist (e.g., "CC" and "Credit Card"), standardize to one value.

<div style="background-color: #FADBD8; border-left: 5px solid #E74C3C; padding: 15px; margin: 15px 0; border-radius: 4px;">
  <strong style="color: #922B21;">🛑 STOP AND CHECK</strong><br>
  Column Distribution for the payment method column should show clean, distinct bars — one per payment type, no duplicates from casing differences.
</div>

---

### Task 4: Resolve Data Type Errors (20 points)

**Menu Items table:**

<div style="background-color: #FEF9E7; border-left: 5px solid #F1C40F; padding: 15px; margin: 15px 0; border-radius: 4px;">
  <strong style="color: #7D6608;">⚠️ COMMON MISTAKE</strong><br>
  The order of operations matters here. If you change the data type <strong>before</strong> removing the dollar sign, the entire column will fill with errors. Always: clean the text first, then change the type.
</div>

1. Select the **Price** column.
2. Use Replace Values to remove the dollar sign: replace **$** with nothing (leave the "Replace With" field empty).
3. **After** the dollar signs are removed, change the data type: click the **ABC** icon next to the Price column name → select **Decimal Number**.

<div style="background-color: #FADBD8; border-left: 5px solid #E74C3C; padding: 15px; margin: 15px 0; border-radius: 4px;">
  <strong style="color: #922B21;">🛑 STOP AND CHECK</strong><br>
  The Price column should show clean numbers (8.50, 12.00, 6.75 — no dollar signs). The data type icon next to the column name should show <strong>"1.2"</strong> (Decimal Number), not "ABC" (Text). Column Quality should show 100% Valid — no errors.<br><br>
  <strong>If you see errors:</strong> Delete the last Applied Steps (click the X next to each in the Applied Steps pane), and start from step 2 again. Remove the "$" first, then change the type.
</div>

---

### Task 5: Apply Naming Conventions (15 points)

**All tables:**

1. Rename columns that use underscores to use spaces instead: `Truck_ID` → `Truck ID`, `Employee_ID` → `Employee ID`, `Menu_Item_ID` → `Menu Item ID`, `Transaction_ID` → `Transaction ID`, and so on. Double-click a column header to edit it.

2. Rename all five queries in the Queries pane (right-click → Rename):
   - `SaborMiami_Sales_2024` (or similar) → **Sales**
   - `SaborMiami_MenuItems` (or similar) → **Menu Items**
   - `SaborMiami_Trucks` (or similar) → **Trucks**
   - `SaborMiami_Employees` (or similar) → **Employees**
   - `SaborMiami_Events_2024` (or similar) → **Events**

<div style="background-color: #FADBD8; border-left: 5px solid #E74C3C; padding: 15px; margin: 15px 0; border-radius: 4px;">
  <strong style="color: #922B21;">🛑 STOP AND CHECK</strong><br>
  Your Queries pane should list five queries with clean names: <strong>Sales, Menu Items, Trucks, Employees, Events</strong>. Column headers across all tables should use spaces, not underscores, and should be descriptive (no abbreviations).
</div>

---

### Task 6: Verify and Reflect (20 points)

**Verification (10 points):**

1. Click through each of the 5 queries.
2. Turn on **Column Quality** (View tab → Data Preview section → Column Quality) for each.
3. Confirm that all columns show **100% Valid** — or close to it. (The Employees phone number column may still show some Empty values — that is expected and correct.)
4. Check the **Applied Steps** pane for each query. Each table should show between 3–8 cleaning steps.

**Written Response (10 points):**

Answer both questions below in 2–3 sentences each. Include your responses in a text file, Word document, or directly in your LMS submission comments.

> **Question 1:** You replaced null Tip values with 0 but left null phone numbers as null. Explain why these two situations required different decisions. What would happen to your calculations if you made the wrong choice in either case?

> **Question 2:** You removed the dollar sign from the Price column before changing the data type. What happens if you reverse that order? Why does the sequence of Applied Steps matter in Power Query?

---

## Submission Instructions

Submit **two items** to your LMS:

1. **Your cleaned .pbix file.** Before submitting, make sure you have clicked **Close & Apply** (Home tab → Close & Apply) in the Power Query Editor to save your cleaning steps and load the cleaned data into the model. Save your .pbix file after closing the Power Query Editor.

2. **Your written response** to the two questions in Task 6. This can be a .txt file, a .docx file, or typed directly into the LMS submission text box.

**File naming convention:** `LastName_FirstName_Lab05.pbix` (e.g., `Garcia_Sofia_Lab05.pbix`)

---

## How Your Work Will Be Evaluated

Your instructor will open your .pbix file and check:

- **Applied Steps pane** for each query — are the cleaning steps present and in a logical order?
- **Column Quality** across all tables — are errors resolved?
- **Column Distribution** for key columns (Category, payment method) — are variants consolidated?
- **Data types** — is the Price column Decimal Number, not Text?
- **Naming** — are queries and columns named clearly with spaces and no abbreviations?
- **Written response** — do your answers demonstrate understanding of the business decisions behind data cleaning, not memorized steps?

<div style="background-color: #D6EAF8; border-left: 5px solid #2E86C1; padding: 15px; margin: 15px 0; border-radius: 4px;">
  <strong style="color: #1A5276;">💡 A NOTE ABOUT THIS ASSIGNMENT</strong><br>
  This lab is not about memorizing which buttons to click — it is about understanding <strong>why</strong> each cleaning decision matters. If you get stuck on a specific step, refer back to the Chapter 5 walkthrough. The goal is a clean dataset and thoughtful written responses, not speed.
</div>

---

> *Lab Assignment 5 of 12 | Chapter 5: Cleaning and Resolving Data Issues*
