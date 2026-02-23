# CAP2791C — Week 9 Graded Lab

## Transforming Text and Numerical Data in Power Query

**Chapter 6 Lab | 100 Points Total**  
**Due:** See course calendar  
**Estimated Time:** 45–60 minutes  
**Tool:** Power BI Desktop → Power Query Editor  
**Dataset:** Sabor Miami (cleaned .pbix from Chapter 5 / provided starter file)

---

## Overview

In this lab, you will apply the transformation techniques from Chapter 6 to the Sabor Miami dataset. You will split and merge text columns, create calculated columns, group and aggregate data, and reshape a table using Unpivot. Each task builds on the skills practiced in the chapter walkthrough, but some steps reduce scaffolding to test your ability to work independently.

**All work is done in the Power Query Editor.** Do not click Close & Apply until all tasks are complete and verified.

---

## What to Submit

Upload the following to the assignment dropbox:

1. **Your completed .pbix file** with all transformations applied and visible in Applied Steps
2. **A written response document** (.docx or .pdf) answering the reflection questions at the end of this lab

---

## Grading Criteria

| Component | Points | What I Am Looking For |
|-----------|--------|----------------------|
| Task 1: Split and Rename | 15 | Column correctly split by delimiter, both columns renamed to clear names |
| Task 2: Merge Columns | 15 | New Display_Name column created in "Last, First" format using Add Column tab (originals preserved) |
| Task 3: Custom Calculated Column | 15 | Total_With_Tip column formula is correct, values verified, data type is Currency or Decimal |
| Task 4: Group By with Multiple Aggregations | 20 | Reference query created (original Sales preserved), grouped by Truck_ID with Sum and Count aggregations, result has exactly 4 rows |
| Task 5: Unpivot | 20 | Correct columns selected for unpivot, Attribute and Value columns renamed meaningfully, table is taller and narrower than the original |
| Reflection Questions | 15 | Thoughtful, specific answers demonstrating understanding — not restating definitions |
| **Total** | **100** | |

---

## Before You Begin

<div style="background-color: #EBF5FB; border: 2px solid #2E86C1; padding: 20px; margin: 15px 0; border-radius: 8px;">
<strong style="font-size: 1.1em;">🚀 LAUNCH PAD</strong><br><br>
<strong>What you are building:</strong> A fully transformed version of the Sabor Miami dataset with five distinct transformations applied<br>
<strong>Tool:</strong> Power BI Desktop → Power Query Editor<br>
<strong>File to open:</strong> SaborMiami_Week9_Starter.pbix<br>
<strong>Data source:</strong> Sales, Employees, and Events tables from the Sabor Miami dataset<br>
<strong>Time estimate:</strong> 45–60 minutes<br>
<strong>What "done" looks like:</strong> Five transformation tasks completed, Applied Steps visible for each modified query, written reflections submitted separately<br>
<strong>Start here →</strong> Open the .pbix file in Power BI Desktop and click Transform Data on the Home tab to enter the Power Query Editor
</div>

**WHERE AM I?** All tasks are completed inside the **Power Query Editor** — the separate window with the green ribbon and the Applied Steps pane on the right. If you do not see the Power Query Editor, click **Transform Data** on the Home tab of the main Power BI Desktop window.

---

## Task 1: Split a Column (15 Points)

**Query:** Employees  
**Goal:** Separate the combined name column into individual First_Name and Last_Name columns.

**Step 1:** In the Queries pane on the left side of the Power Query Editor, click the **Employees** query.

**Step 2:** Identify the column that contains full names (first and last name combined in a single column). Click that column header to select it.

**Step 3:** Navigate to **Transform tab → Split Column → By Delimiter**.

**Step 4:** In the Split Column by Delimiter dialog:
- Select the appropriate delimiter (the character separating the first and last names — most likely a **space**).
- Choose **At the left-most delimiter** (this handles cases where someone might have a middle name or initial — it splits only at the first space).
- Click **OK**.

**Step 5:** Rename the two resulting columns:
- Right-click the first new column header → **Rename** → type **First_Name**
- Right-click the second new column header → **Rename** → type **Last_Name**

<div style="background-color: #FADBD8; border-left: 5px solid #E74C3C; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #922B21;">🛑 STOP AND CHECK</strong><br>
Your Employees table should now have separate <strong>First_Name</strong> and <strong>Last_Name</strong> columns instead of the original combined name column. Scan several rows to confirm the split worked correctly — first names in one column, last names in the other. Check your Applied Steps pane: you should see at least 2 new steps (the split and the renames).
</div>

---

## Task 2: Merge Columns into a Display Name (15 Points)

**Query:** Employees (continuing from Task 1)  
**Goal:** Create a new Display_Name column in "Last, First" format while keeping the original First_Name and Last_Name columns intact.

**Step 1:** Select both the **Last_Name** and **First_Name** columns. Click **Last_Name** first, then hold **Ctrl** and click **First_Name**.

**Step 2:** Navigate to the **Add Column tab** (not the Transform tab — you need to keep the original columns).

**Step 3:** Click **Merge Columns**.

**Step 4:** In the Merge Columns dialog:
- Select **Custom** from the Separator dropdown.
- Type a comma followed by a space: **, **
- In the New column name field, type **Display_Name**.
- Click **OK**.

<div style="background-color: #FADBD8; border-left: 5px solid #E74C3C; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #922B21;">🛑 STOP AND CHECK</strong><br>
You should now have <strong>three</strong> name columns: First_Name, Last_Name, and Display_Name. The Display_Name values should look like "Santos, Maria" — last name, comma, space, first name. If the original First_Name and Last_Name columns disappeared, you used the Transform tab instead of the Add Column tab. Undo the step (click the X in Applied Steps) and redo it using the <strong>Add Column tab</strong>.
</div>

---

## Task 3: Create a Custom Calculated Column (15 Points)

**Query:** Sales  
**Goal:** Add a column that calculates the total transaction amount including tip.

**Step 1:** In the Queries pane, click the **Sales** query.

**Step 2:** Before creating the column, verify that the **Amount** and **Tip** columns have numerical data types. Check the icon to the left of each column header:
- **$** or **1.2** = numerical (good)
- **ABC** = Text (needs to be changed — click the icon and select **Currency**)

**Step 3:** Navigate to **Add Column tab → Custom Column**.

**Step 4:** In the Custom Column dialog:
- New column name: **Total_With_Tip**
- Formula: `[Amount] + [Tip]`
- Click **OK**.

**Step 5:** Verify the data type of your new column. If it is not Currency or Decimal Number, click the data type icon to the left of the **Total_With_Tip** column header and select **Currency**.

<div style="background-color: #FADBD8; border-left: 5px solid #E74C3C; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #922B21;">🛑 STOP AND CHECK</strong><br>
Scroll to the right side of your Sales table. The Total_With_Tip column should show values that equal Amount + Tip for every row. Spot-check at least 3 rows by adding the values mentally. If any rows show <strong>Error</strong>, the Tip column likely has null values — you can handle this by modifying the formula to: <code>[Amount] + (if [Tip] = null then 0 else [Tip])</code>
</div>

---

## Task 4: Group By with Multiple Aggregations (20 Points)

**Query:** Create a new Reference query from Sales  
**Goal:** Produce a per-truck summary showing total sales and transaction count.

This task is worth the most points because it tests multiple skills: creating a reference query, using Advanced Group By, and verifying the output.

**Step 1:** In the Queries pane, right-click the **Sales** query and select **Reference**. This creates a new query that points to the same data without modifying the original.

**Step 2:** Right-click the new query (it may be named "Sales (2)") and select **Rename**. Type **Sales_By_Truck**.

**Step 3:** With the Sales_By_Truck query selected, click the **Group By** button (Transform tab → Table section).

**Step 4:** In the Group By dialog:
- Click the **Advanced** option at the top.
- **Group by:** Truck_ID
- First aggregation — **New column name:** Total_Sales | **Operation:** Sum | **Column:** Amount
- Click **Add aggregation** to add a second row.
- Second aggregation — **New column name:** Transaction_Count | **Operation:** Count Rows

**Step 5:** Click **OK**.

<div style="background-color: #FADBD8; border-left: 5px solid #E74C3C; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #922B21;">🛑 STOP AND CHECK</strong><br>
Your Sales_By_Truck query should have exactly <strong>4 rows</strong> (one for each Sabor Miami truck: T001, T002, T003, T004) and <strong>3 columns</strong> (Truck_ID, Total_Sales, Transaction_Count). If you see more than 4 rows, check that you grouped by Truck_ID. Also confirm that the original <strong>Sales</strong> query still has all its detail rows — click back on Sales in the Queries pane to verify it is untouched.
</div>

---

## Task 5: Unpivot Columns (20 Points)

**Query:** Events (or a Reference copy)  
**Goal:** Convert wide-format columns into tall-format rows suitable for a data model.

The scaffolding decreases for this task. You have the concepts from the chapter — now apply them.

**Step 1:** In the Queries pane, examine the **Events** query. Identify which columns represent categories or time periods as separate column headers (wide format) instead of row values. These are the columns you will unpivot.

> **Hint:** If you are unsure which columns to unpivot, ask yourself: "Are these column headers values that should be in a single column?" For example, if you see month names or event type names as column headers, those should probably be row values.

**Step 2:** Create a **Reference** copy of the Events query to preserve the original. Rename the reference to something descriptive (for example, **Events_Unpivoted**).

**Step 3:** Select the columns you want to **keep** as they are (such as an ID column or a name column). Then use **Unpivot Other Columns** (Transform tab → Any Column section). This approach is safer than selecting individual columns to unpivot because it automatically handles any new columns that might be added in future data refreshes.

**Step 4:** Rename the resulting **Attribute** column and **Value** column to meaningful names that describe what they contain.

<div style="background-color: #FADBD8; border-left: 5px solid #E74C3C; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #922B21;">🛑 STOP AND CHECK</strong><br>
Compare your unpivoted table to the original Events table:
<ul>
<li>The unpivoted table should have <strong>more rows</strong> and <strong>fewer columns</strong> than the original</li>
<li>The old column headers should now appear as values in your renamed Attribute column</li>
<li>The numbers from those old columns should appear in your renamed Value column</li>
<li>The columns you chose to keep should be unchanged and repeated across the new rows</li>
</ul>
</div>

---

## Final Verification

Before saving your file, do a final pass through the Queries pane:

| Query | What to Verify |
|-------|---------------|
| **Employees** | First_Name, Last_Name, and Display_Name columns all present. Display_Name format: "Last, First" |
| **Sales** | Total_With_Tip column present. Values are correct (Amount + Tip). Data type is Currency or Decimal |
| **Sales_By_Truck** | Reference query. 4 rows, 3 columns (Truck_ID, Total_Sales, Transaction_Count) |
| **Events_Unpivoted** (or your name) | Reference query. Taller than original Events. Attribute and Value columns renamed |
| **Original Sales and Events** | Still intact with all original detail rows — not modified by your Group By or Unpivot work |

When everything checks out, click **Close & Apply** (Home tab → Close & Apply) to save your Power Query work and load it into the data model. Then save the .pbix file.

---

## Reflection Questions (15 Points)

Answer the following in your written response document. Each answer should be **2–4 sentences**. I am looking for your understanding of the concepts, not restated definitions from the textbook.

**Question 1 (5 points):** In Task 4, you created a Reference query before applying Group By instead of grouping the original Sales query directly. Explain in your own words why this step was necessary. What would have happened to your data if you had skipped it?

**Question 2 (5 points):** Think about the Unpivot operation you performed in Task 5. Describe a real-world scenario — from a job, an internship, a class, or your personal life — where you might receive data in a wide format that would need to be unpivoted before analysis. What would the column headers be, and what would the resulting tall table look like?

**Question 3 (5 points):** In this lab, you used both the **Transform tab** and the **Add Column tab** for different tasks. Explain the key difference between them and describe a situation where choosing the wrong tab could cause a problem you would need to undo.

---

## Bonus Challenge (Optional — Up to 5 Extra Credit Points)

Create a second Group By reference query called **Sales_By_Truck_By_Event** that groups the Sales data by **two columns**: Truck_ID and Event_ID (or the equivalent event-linking column in your dataset). Include three aggregations: Total Sales (Sum of Amount), Average Transaction (Average of Amount), and Total Tips (Sum of Tip).

This requires using the **Add grouping** button in the Advanced Group By dialog to add a second grouping column — a feature not explicitly demonstrated in the chapter walkthrough. Experiment with the dialog to figure out where this button is and how it works.

<div style="background-color: #FADBD8; border-left: 5px solid #E74C3C; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #922B21;">🛑 STOP AND CHECK (Bonus)</strong><br>
Your Sales_By_Truck_By_Event query should have more than 4 rows (because each truck participates in multiple events) but far fewer rows than the original Sales table. It should have <strong>5 columns</strong>: Truck_ID, Event_ID, Total_Sales, Avg_Transaction, and Total_Tips. If you see only 4 rows, you may have forgotten to add Event_ID as a second grouping column.
</div>

---

## Submission Checklist

Before submitting, confirm:

- [ ] .pbix file saved with all 5 tasks completed (Tasks 1–5 visible in Applied Steps for each modified query)
- [ ] Original Sales and Events queries are preserved (not overwritten by Group By or Unpivot)
- [ ] All new columns have clear, descriptive names (no "Column1" or "Full_Name.1" leftovers)
- [ ] Written response document includes answers to all 3 reflection questions
- [ ] (Optional) Bonus challenge query included if attempting extra credit

Upload both files to the Week 9 assignment dropbox.

---

> **Reminder:** If you get stuck on any task, re-read the corresponding section in Chapter 6. The walkthrough steps in the chapter mirror what you are doing here. The chapter's STOP AND CHECK boxes describe exactly what your screen should look like at each stage.
