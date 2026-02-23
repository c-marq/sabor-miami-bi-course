# Graded Lab #1: Data Cleaning

**CAP2791C: Power BI Data Preparation and Modeling | ND Section**  
**Week 9 Session B | 50 Points**

---

## Assignment Overview

| | |
|---|---|
| **Lab** | Graded Lab #1 of 4 |
| **Chapter** | Chapter 5 — Cleaning and Resolving Data Issues |
| **Competencies** | C3.1, C3.2, C3.7, C3.9 · PL-300: Clean |
| **Tool** | Power BI Desktop → Power Query Editor |
| **File to open** | Your Sabor Miami .pbix file (with all 5 tables connected) |
| **Time estimate** | 45–55 minutes |
| **Points** | 50 points |
| **What you submit** | Your cleaned .pbix file + short written response (2 questions) |

---

## Policies for This Lab

- **Late work:** 48-hour grace period (no penalty). After 48 hours: 10% per day, max 30% off.
- **Redo option:** If you score below "Good" (30 pts), you may revise and resubmit once for up to the Good tier score.
- **Submission formats:** (1) your .pbix file, and (2) written response as a .txt, .docx, or typed directly into Canvas submission comments.

---

## What You Are Doing

In Week 8, you profiled all five Sabor Miami tables and documented data quality issues in your Data Quality Snapshot. In this lab, you **fix those issues** using the cleaning techniques from Chapter 5. By the end, your dataset should have no unresolved errors, consistent text values, correct data types, and clear column and query names.

If you get stuck on any task, refer back to the Chapter 5 walkthrough for step-by-step guidance.

---

## Grading Rubric

Rubric is provided upfront so you know exactly what to aim for.

| Tier | Points | What It Looks Like |
|------|--------|--------------------|
| **Excellent** | 45–50 | All 5 tasks completed correctly. Column Quality shows 100% Valid (or near-100% with justified nulls). Naming is clean and consistent. Written response demonstrates understanding of WHY, not just WHAT. |
| **Good** | 30–44 | Most tasks completed. Minor issues remain (1–2 inconsistencies, a missed rename, or a data type not fully corrected). Written response addresses both questions but may lack depth. |
| **Needs Work** | 0–29 | Multiple tasks incomplete or incorrect. Errors remain in Column Quality. Written response missing or restates steps without explaining reasoning. Eligible for redo. |

### Points by Task

| Task | Points | What I Am Looking For |
|------|--------|-----------------------|
| **Task 1:** Resolve null values | 8 pts | Null tips replaced with 0 in Sales. Null phone numbers left as null in Employees. Both decisions visible in Applied Steps. |
| **Task 2:** Fix text inconsistencies | 10 pts | Menu Items categories standardized. Employee names in Proper Case. Truck location typo corrected. Trailing spaces trimmed. |
| **Task 3:** Standardize values | 5 pts | Payment methods use consistent casing. No duplicate variants in Column Distribution. |
| **Task 4:** Resolve data type errors | 10 pts | Dollar signs removed from Price column BEFORE changing type. Price is Decimal Number, not Text. No errors. |
| **Task 5:** Apply naming conventions | 7 pts | Columns use spaces instead of underscores. All 5 queries renamed to clean names. |
| **Written response** | 10 pts | Two questions answered thoughtfully (2–3 sentences each). Demonstrates understanding of business decisions behind cleaning choices. |
| **TOTAL** | **50 pts** | |

---

## Before You Begin

<div style="background-color: #1a1a2e; border: 2px solid #16a085; padding: 20px; margin: 15px 0; border-radius: 8px;">
  <strong style="color: #16a085; font-size: 1.1em;">🚀 LAUNCH PAD</strong><br><br>
  <strong>What you are building:</strong> A fully cleaned version of the Sabor Miami dataset<br>
  <strong>Tool:</strong> Power BI Desktop → Power Query Editor<br>
  <strong>File to open:</strong> Your .pbix file with all 5 Sabor Miami tables<br>
  <strong>Time estimate:</strong> 45–55 minutes<br>
  <strong>Number of tasks:</strong> 5 tasks + written response<br>
  <strong>What "done" looks like:</strong> All 5 tables cleaned — no errors, consistent text, correct data types, clear names<br>
  <strong>Start here →</strong> Open your .pbix file and click <strong>Transform Data</strong> on the Home tab
</div>

> **WHERE AM I?** All tasks in this lab take place in the **Power Query Editor** — the separate window with the green ribbon. If you see the main Power BI canvas with the Visualizations pane, you are in the wrong window. Click **Transform Data** on the Home tab to open the Power Query Editor.

---

## What Success Looks Like

When you are done, your Power Query Editor should show:

- **5 queries** in the Queries pane with clean names: **Sales, Menu Items, Trucks, Employees, Events**
- **Column Quality bars** showing 100% Valid on all columns (except Employees phone numbers, which may show some Empty — that is correct)
- **Applied Steps** pane for each query showing 3–8 cleaning steps
- **No dollar signs** in the Price column (Menu Items), and the data type icon shows **1.2** (Decimal Number), not **ABC** (Text)
- **Column Distribution** for Menu Items Category and Sales Payment Method showing clean, distinct bars — no duplicates from casing

---

## Tasks

### Task 1: Resolve Null Values (8 points)

**Phase: Setup → Explore → Build → Verify**

**Sales table:**

1. Click the **Sales** query in the Queries pane (left side of the Power Query Editor).
2. Click on the **Tip** column header to select it.
3. Go to **Transform tab** → click **Replace Values**.
4. In the Replace Values dialog: **Value to Find** = `null` · **Replace With** = `0` · click **OK**.

**Employees table:**

5. Click the **Employees** query in the Queries pane.
6. Check for null values in the phone number column. **Do not replace these.** A missing phone number does not mean the number is zero — it means the employee did not provide one.

<div style="background-color: #FADBD8; border-left: 5px solid #E74C3C; padding: 15px; margin: 15px 0; border-radius: 4px;">
  <strong style="color: #922B21;">🛑 STOP AND CHECK</strong><br>
  <strong>Sales table:</strong> Scroll through the Tip column. You should see <strong>0</strong> where nulls used to be. The Applied Steps pane should show a new step called "Replaced Value."<br><br>
  <strong>Employees table:</strong> Null phone numbers should still appear as <strong>null</strong> — no changes made.
</div>

---

### Task 2: Fix Text Inconsistencies (10 points)

**Menu Items table:**

1. Click the **Menu Items** query (or whatever it is currently named) in the Queries pane.
2. Click on the **Category** column header.
3. Use **Transform tab → Replace Values** to fix each variant:
   - Replace `Entree` with `Entrée`
   - Replace `entree` with `Entrée`
   - Repeat for any other inconsistent categories you find (check Column Distribution to see all variants)

**Employees table:**

4. Click the **Employees** query.
5. Click the **First Name** column header (or First_Name).
6. Go to **Transform tab → Format → Capitalize Each Word** (this applies Proper Case).
7. Repeat for the **Last Name** column.
8. With each name column selected, go to **Transform tab → Format → Trim** to remove trailing spaces.

**Trucks table:**

9. Click the **Trucks** query.
10. Use **Replace Values** on the location column to fix `Kendal` → `Kendall`.

<div style="background-color: #FADBD8; border-left: 5px solid #E74C3C; padding: 15px; margin: 15px 0; border-radius: 4px;">
  <strong style="color: #922B21;">🛑 STOP AND CHECK</strong><br>
  Turn on <strong>Column Distribution</strong> (View tab → Data Preview section → check Column Distribution) for the Category column in Menu Items. The number of distinct values should match the actual number of categories — no duplicates from casing or spelling.<br><br>
  In Employees, all names should be in consistent Proper Case format (e.g., "Maria Garcia," not "MARIA GARCIA" or "maria garcia").
</div>

---

<div style="background-color: #E8DAEF; border-left: 5px solid #8E44AD; padding: 15px; margin: 15px 0; border-radius: 4px;">
  <strong style="color: #6C3483;">💜 TAKE A BREATH</strong><br>
  You are halfway through. Tasks 1 and 2 are the most tedious part — lots of Replace Values clicks. The remaining tasks go faster. Stretch if you need to.
</div>

---

### Task 3: Standardize Values (5 points)

**Sales table:**

1. Click the **Sales** query.
2. Click on the **Payment Method** column header (or Payment_Method).
3. Use **Replace Values** to standardize all casing variants to one consistent form:
   - `CASH` → `Cash`
   - `cash` → `Cash`
   - Do the same for any credit card variants (e.g., `CREDIT` → `Credit Card`, `cc` → `Credit Card`)

<div style="background-color: #FADBD8; border-left: 5px solid #E74C3C; padding: 15px; margin: 15px 0; border-radius: 4px;">
  <strong style="color: #922B21;">🛑 STOP AND CHECK</strong><br>
  Column Distribution for the Payment Method column should show clean, distinct bars — one bar per payment type, no duplicates from casing differences.
</div>

---

### Task 4: Resolve Data Type Errors (10 points)

**Menu Items table:**

<div style="background-color: #FEF9E7; border-left: 5px solid #F1C40F; padding: 15px; margin: 15px 0; border-radius: 4px;">
  <strong style="color: #7D6608;">⚠️ COMMON MISTAKE</strong><br>
  The order of operations matters here. If you change the data type <strong>before</strong> removing the dollar sign, the entire column will fill with errors. Always: clean the text first, THEN change the type.
</div>

1. Click the **Menu Items** query.
2. Click the **Price** column header.
3. Use **Replace Values** to remove the dollar sign: **Value to Find** = `$` · **Replace With** = *(leave empty)* · click **OK**.
4. **After** the dollar signs are removed, change the data type: click the **ABC** icon to the left of the Price column header → select **Decimal Number**.

<div style="background-color: #FADBD8; border-left: 5px solid #E74C3C; padding: 15px; margin: 15px 0; border-radius: 4px;">
  <strong style="color: #922B21;">🛑 STOP AND CHECK</strong><br>
  The Price column should show clean numbers (8.50, 12.00, 6.75 — no dollar signs). The data type icon next to the column name should show <strong>1.2</strong> (Decimal Number), not <strong>ABC</strong> (Text). Column Quality should show 100% Valid — no errors.<br><br>
  <strong>If you see errors:</strong> Delete the last Applied Steps by clicking the <strong>X</strong> next to each step in the Applied Steps pane. Then start from step 3 again — remove the "$" first, then change the type.
</div>

---

### Task 5: Apply Naming Conventions (7 points)

**All tables:**

1. Rename columns that use underscores to use spaces instead. Double-click a column header to edit it:
   - `Truck_ID` → `Truck ID`
   - `Employee_ID` → `Employee ID`
   - `Menu_Item_ID` → `Menu Item ID`
   - `Transaction_ID` → `Transaction ID`
   - Apply the same pattern to any other columns that use underscores

2. Rename all five queries in the Queries pane. Right-click a query → **Rename**:
   - `SaborMiami_Sales_2024` (or similar) → **Sales**
   - `SaborMiami_MenuItems` (or similar) → **Menu Items**
   - `SaborMiami_Trucks` (or similar) → **Trucks**
   - `SaborMiami_Employees` (or similar) → **Employees**
   - `SaborMiami_Events_2024` (or similar) → **Events**

<div style="background-color: #FADBD8; border-left: 5px solid #E74C3C; padding: 15px; margin: 15px 0; border-radius: 4px;">
  <strong style="color: #922B21;">🛑 STOP AND CHECK</strong><br>
  Your Queries pane should list five queries with clean names: <strong>Sales, Menu Items, Trucks, Employees, Events</strong>. Column headers across all tables should use spaces, not underscores.
</div>

---

## Save and Submit

1. Click **Close & Apply** in the Power Query Editor (Home tab → Close & Apply). This saves your cleaning steps and loads the cleaned data into the model.
2. Save your .pbix file: **File → Save As → `LastName_FirstName_Lab01.pbix`**
3. Answer the two written response questions below.
4. Submit both your .pbix file and your written response to the **Lab #1** assignment in Canvas.

---

## Written Response (10 points)

Answer both questions in 2–3 sentences each. Include your responses in a .txt file, .docx file, or type them directly into the Canvas submission comments.

> **Question 1:** You replaced null Tip values with 0 but left null phone numbers as null. Explain why these two situations required different decisions. What would happen to your calculations if you made the wrong choice in either case?

> **Question 2:** You removed the dollar sign from the Price column before changing the data type. What happens if you reverse that order? Why does the sequence of Applied Steps matter in Power Query?

---

## How Your Work Will Be Evaluated

Your instructor will open your .pbix file and check:

- **Applied Steps pane** for each query — are the cleaning steps present and in a logical order?
- **Column Quality** across all tables — are errors resolved?
- **Column Distribution** for key columns (Category, Payment Method) — are variants consolidated?
- **Data types** — is Price Decimal Number, not Text?
- **Naming** — are queries and columns named clearly?
- **Written response** — do your answers demonstrate understanding of the business decisions behind data cleaning?

<div style="background-color: #D6EAF8; border-left: 5px solid #2E86C1; padding: 15px; margin: 15px 0; border-radius: 4px;">
  <strong style="color: #1A5276;">💡 A NOTE ABOUT THIS LAB</strong><br>
  This lab is not about memorizing which buttons to click — it is about understanding <strong>why</strong> each cleaning decision matters. The goal is a clean dataset and thoughtful written responses, not speed. If you finish early, go back through each table and check for any issues you may have missed.
</div>

---

> *Graded Lab 1 of 4 | Week 9 | Chapter 5: Cleaning and Resolving Data Issues*  
> *Late policy: 48-hour grace period, then 10%/day, max 30% off. Redo available if below 30 pts.*
