# Week 10 Practice Worksheet: Transforming and Reshaping Data

**CAP2791C: Power BI Data Preparation and Modeling | ND Section**  
**Week 10 Session B | Ungraded Practice**  
**Chapter 6 Skills Reinforcement**

---

## 🚀 LAUNCH PAD

| | |
|---|---|
| **What you are building** | Six specific transformations applied to your cleaned Sabor Miami dataset |
| **Tool** | Power BI Desktop → Power Query Editor |
| **File to open** | Your cleaned .pbix file from Lab #1 (the one you submitted with clean names and no errors) |
| **Time estimate** | 30–40 minutes |
| **Number of tasks** | 6 tasks across 3 phases |
| **What "done" looks like** | Employees table has split name columns and a Display Name column. Sales table has a Total With Tip column. Two new reference queries show grouped summaries. |
| **Start here →** | Open your Lab #1 .pbix file and click **Transform Data** on the Home tab to enter the Power Query Editor |

---

> **WHERE AM I?** All six tasks happen inside the **Power Query Editor** — the separate window with the green ribbon and the Applied Steps pane on the right. If you see the main Power BI canvas with the Visualizations pane, you are in the wrong window. Click **Transform Data** on the Home tab to open the Power Query Editor.

---

> **Important:** This worksheet is **not graded**. It is practice. The six skills you practice here are the same skills you will need for Lab #2 next week. Treat this as rehearsal — try each task, check your work, and ask questions if something does not match.

---

## Phase 1 of 3: Text Transformations (Tasks 1–3)

These three tasks use the **Employees** table and the **Trucks** table.

---

### Task 1 — Split a Column

**What you are doing:** Splitting the full name column in the Employees table into separate First Name and Last Name columns.

**Which query:** Click the **Employees** query in the Queries pane on the left.

**Before you start:** Look at the Employees table. Find the column that contains employee names. After Lab #1, your names should be in Proper Case (for example, "Maria Santos"). This column may be called **Full Name**, **Employee Name**, or **Name** — use whatever your cleaned version shows.

<div style="background-color: #D5F5E3; border-left: 5px solid #27AE60; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #1E8449;">✅ DO THIS</strong><br>

**Step 1:** Click the **name column header** to select it.

**Step 2:** Go to the **Transform tab** on the ribbon (the green bar at the top of the Power Query Editor).

**Step 3:** Click the **Split Column** button — it is in the **Text Column** section, toward the right side of the ribbon.

**Step 4:** Select **By Delimiter** from the dropdown menu.

**Step 5:** In the Split Column by Delimiter dialog:
- Select **Space** from the delimiter dropdown.
- Select **At the left-most delimiter** (this handles names with middle names or double last names by splitting only at the first space).
- Click **OK**.

</div>

<div style="background-color: #FADBD8; border-left: 5px solid #E74C3C; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #922B21;">🛑 STOP AND CHECK</strong><br>
Your name column should be gone. In its place, you should see two new columns with auto-generated names (something like <code>Name.1</code> and <code>Name.2</code>). The first column contains first names. The second column contains last names.<br><br>
Now rename them: double-click the first column header and type <strong>First Name</strong>. Double-click the second column header and type <strong>Last Name</strong>.<br><br>
Check the <strong>Applied Steps</strong> pane on the right — you should see a "Split Column by Delimiter" step and one or two "Renamed Columns" steps.
</div>

---

### Task 2 — Merge Columns

**What you are doing:** Combining the two name columns back together in "Last, First" format to create a Display Name column — while keeping the originals.

**Which query:** Stay on the **Employees** query.

<div style="background-color: #D6EAF8; border-left: 5px solid #2E86C1; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #1A5276;">💡 WHY ARE WE DOING THIS?</strong><br>
Chapter 6 taught an important distinction: the <strong>Transform tab</strong> replaces existing columns, while the <strong>Add Column tab</strong> keeps the originals and creates a new column. In this task, we want to keep First Name and Last Name AND create a Display Name. That means we use the <strong>Add Column tab</strong>, not the Transform tab.
</div>

<div style="background-color: #D5F5E3; border-left: 5px solid #27AE60; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #1E8449;">✅ DO THIS</strong><br>

**Step 1:** Select both name columns. Click **Last Name** first, then hold **Ctrl** and click **First Name**.

**Step 2:** Go to the **Add Column tab** on the ribbon (not the Transform tab).

**Step 3:** Click the **Merge Columns** button — it is in the **Text** section of the Add Column ribbon.

**Step 4:** In the Merge Columns dialog:
- Select **Custom** from the Separator dropdown.
- Type a comma followed by a space: `, ` (comma then one space).
- In the **New column name** field, type: `Display Name`
- Click **OK**.

</div>

<div style="background-color: #FADBD8; border-left: 5px solid #E74C3C; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #922B21;">🛑 STOP AND CHECK</strong><br>
You should now see <strong>three</strong> name-related columns: <strong>First Name</strong>, <strong>Last Name</strong>, and <strong>Display Name</strong>. The Display Name values should look like "Santos, Maria" or "Delgado, Jorge".<br><br>
<strong>If First Name and Last Name disappeared</strong>, you used the Transform tab instead of the Add Column tab. Click the <strong>X</strong> next to the last step in Applied Steps to undo it, then try again using the <strong>Add Column tab</strong>.
</div>

---

### Task 3 — Extract Characters

**What you are doing:** Pulling the first character of the Truck ID column to create a Truck Prefix column. This gives a quick way to identify the series a truck belongs to.

**Which query:** Click the **Trucks** query in the Queries pane.

<div style="background-color: #D5F5E3; border-left: 5px solid #27AE60; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #1E8449;">✅ DO THIS</strong><br>

**Step 1:** Click the **Truck ID** column header to select it.

**Step 2:** Go to the **Add Column tab** on the ribbon (we want to keep the original Truck ID column).

**Step 3:** Click **Extract** in the **From Text** section of the ribbon, then select **First Characters** from the dropdown.

**Step 4:** In the dialog, type `1` for the number of characters. Click **OK**.

**Step 5:** Rename the new column from "First Characters" to **Truck Prefix**.

</div>

<div style="background-color: #FADBD8; border-left: 5px solid #E74C3C; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #922B21;">🛑 STOP AND CHECK</strong><br>
The Trucks table should have a new column called <strong>Truck Prefix</strong> containing a single character (for example, "T" for all trucks starting with T). Your original <strong>Truck ID</strong> column should still be intact next to it.
</div>

---

<div style="background-color: #E8DAEF; border-left: 5px solid #8E44AD; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #6C3483;">💜 TAKE A BREATH</strong><br>
You just completed the text transformation phase — Split, Merge, and Extract. These three operations reshape text columns without changing the underlying data. Take a moment to stretch or look away from your screen. The next phase works with numbers.
</div>

---

## Phase 2 of 3: Numerical Transformations (Task 4)

This task uses the **Sales** table.

---

### Task 4 — Create a Custom Calculated Column

**What you are doing:** Adding a new column to Sales that calculates the total amount including the tip: Amount + Tip.

**Which query:** Click the **Sales** query in the Queries pane.

**Before you start:** Confirm that your Amount and Tip columns have numerical data types. Look at the icon to the left of each column header: it should show **1.2** (Decimal Number) or **$** (Currency), not **ABC** (Text). If either column shows ABC, change the data type first by clicking the icon and selecting **Currency**.

<div style="background-color: #D5F5E3; border-left: 5px solid #27AE60; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #1E8449;">✅ DO THIS</strong><br>

**Step 1:** Make sure you are on the **Sales** query.

**Step 2:** Go to the **Add Column tab** on the ribbon.

**Step 3:** Click the **Custom Column** button — it is in the **General** section on the left side of the Add Column ribbon.

**Step 4:** In the Custom Column dialog:
- In the **New column name** field, type: `Total With Tip`
- In the **Custom column formula** field, type: `[Amount] + [Tip]`
- Notice: column names go inside square brackets. Use the exact column names from your table.
- Click **OK**.

</div>

<div style="background-color: #FEF9E7; border-left: 5px solid #F1C40F; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #7D6608;">⚠️ COMMON MISTAKE</strong><br>
If you see <strong>Error</strong> in some rows of your new column, the most likely cause is that some Tip values are null. In Lab #1, you should have replaced null tips with 0. If you skipped that step, go back to the Tip column now: <strong>Transform tab → Replace Values → Value to Find:</strong> <code>null</code> <strong>→ Replace With:</strong> <code>0</code>. Then your custom column formula should work without errors.
</div>

<div style="background-color: #FADBD8; border-left: 5px solid #E74C3C; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #922B21;">🛑 STOP AND CHECK</strong><br>
Scroll to the right side of the Sales table. You should see a new column called <strong>Total With Tip</strong>. Spot-check a few rows: if Amount is 15.00 and Tip is 2.00, Total With Tip should be 17.00. If Amount is 8.50 and Tip is 0, Total With Tip should be 8.50.
</div>

---

## Phase 3 of 3: Grouping and Summarizing (Tasks 5–6)

These tasks create summary views of the Sales data using Group By. Because Group By replaces the original table with a summary, you will create **Reference queries** first so your full Sales data stays intact.

<div style="background-color: #D6EAF8; border-left: 5px solid #2E86C1; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #1A5276;">💡 WHY ARE WE DOING THIS?</strong><br>
In your database course (Course 2), you used <code>GROUP BY</code> in SQL to summarize rows:<br><br>
<code>SELECT Truck_ID, SUM(Amount) AS Total_Sales FROM Sales GROUP BY Truck_ID;</code><br><br>
Power Query's <strong>Group By</strong> button does the same thing — visually. You select a column to group on, choose an aggregation (sum, average, count), and Power Query collapses the rows into a summary. Same logic, different interface.<br><br>
<strong>Why Reference first?</strong> Group By replaces the table. If you group the Sales query directly, all your detail rows disappear. A <strong>Reference query</strong> points to the same data without copying it. You group the reference, and the original stays untouched.
</div>

---

### Task 5 — Group By: Total Sales Per Truck

**What you are doing:** Creating a summary showing total sales amount for each truck.

<div style="background-color: #D5F5E3; border-left: 5px solid #27AE60; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #1E8449;">✅ DO THIS</strong><br>

**Step 1:** In the Queries pane, **right-click** the **Sales** query and select **Reference**. A new query appears called "Sales (2)" or similar.

**Step 2:** Rename this new query. Right-click it → **Rename** → type: `Sales By Truck`

**Step 3:** With the **Sales By Truck** query selected, click the **Group By** button.
- **Find It:** It is in the **Transform tab**, in the **Table** section (left side of the ribbon). It is also available in the **Home tab**.

**Step 4:** In the Group By dialog (make sure **Basic** is selected):
- **Group by:** `Truck ID`
- **New column name:** `Total Sales`
- **Operation:** `Sum`
- **Column:** `Amount`
- Click **OK**.

</div>

<div style="background-color: #FADBD8; border-left: 5px solid #E74C3C; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #922B21;">🛑 STOP AND CHECK</strong><br>

Check these three things:

1. **Row count:** The Sales By Truck query should show exactly **4 rows** — one for each truck (T001, T002, T003, T004). If you see more than 4 rows, check that you grouped by Truck ID and not a different column.

2. **Columns:** You should see exactly **2 columns** — Truck ID and Total Sales.

3. **Original data intact:** Click the **Sales** query in the Queries pane. It should still have all of its original detail rows (hundreds or thousands of rows). The grouping only happened on the reference query.

</div>

---

### Task 6 — Group By: Transaction Count Per Payment Method

**What you are doing:** Creating a summary showing how many transactions used each payment method.

<div style="background-color: #D5F5E3; border-left: 5px solid #27AE60; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #1E8449;">✅ DO THIS</strong><br>

**Step 1:** In the Queries pane, **right-click** the **Sales** query again and select **Reference**. A new query appears.

**Step 2:** Rename this query to: `Sales By Payment Method`

**Step 3:** With the **Sales By Payment Method** query selected, click the **Group By** button (Transform tab → Table section).

**Step 4:** In the Group By dialog (Basic mode):
- **Group by:** `Payment Method`
- **New column name:** `Transaction Count`
- **Operation:** `Count Rows`
- Click **OK**.

</div>

<div style="background-color: #FEF9E7; border-left: 5px solid #F1C40F; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #7D6608;">⚠️ COMMON MISTAKE</strong><br>
When using <strong>Count Rows</strong> as the operation, you do <strong>not</strong> need to select a column in the Column dropdown — Count Rows counts the entire row, not a specific column. If the Column dropdown is grayed out, that is correct.
</div>

<div style="background-color: #FADBD8; border-left: 5px solid #E74C3C; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #922B21;">🛑 STOP AND CHECK</strong><br>

Check these three things:

1. **Row count:** The Sales By Payment Method query should show one row per payment type. After Lab #1 standardization, you should see clean, distinct payment methods (for example: Cash, Credit Card, and possibly one or two others). If you see duplicate-looking rows (like "Cash" and "cash"), your Lab #1 standardization may need a fix.

2. **Columns:** You should see exactly **2 columns** — Payment Method and Transaction Count.

3. **Math check:** Add up all the Transaction Count values mentally or on paper. The total should equal the total number of rows in your original Sales query. (This is how you verify that no rows were lost or double-counted during grouping.)

</div>

---

<div style="background-color: #E8DAEF; border-left: 5px solid #8E44AD; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #6C3483;">💜 TAKE A BREATH</strong><br>
You just completed all six tasks. That is every major transformation type from Chapter 6: Split, Merge, Extract, Custom Column, and two versions of Group By. These are the same skills you will use in Lab #2 next week when you combine tables. Save your file.
</div>

---

## Final Checklist

Before you close, confirm:

| ✓ | What to Check | Where to Look |
|---|---|---|
| ☐ | Employees has **First Name**, **Last Name**, and **Display Name** columns | Click Employees query → scan column headers |
| ☐ | Trucks has a **Truck Prefix** column (original Truck ID still intact) | Click Trucks query → scan column headers |
| ☐ | Sales has a **Total With Tip** column with correct values | Click Sales query → scroll right → spot-check a few rows |
| ☐ | **Sales By Truck** query shows 4 rows with Truck ID and Total Sales | Click Sales By Truck query → check row count and columns |
| ☐ | **Sales By Payment Method** query shows one row per payment type | Click Sales By Payment Method query → check for duplicates |
| ☐ | Original **Sales** query still has all detail rows | Click Sales query → confirm row count has not changed |
| ☐ | **Applied Steps** pane shows transformation steps for each modified query | Click through each query → check Applied Steps |

---

## Do Not Close & Apply Yet

You have two new reference queries (Sales By Truck and Sales By Payment Method) that were useful for practice but are **not part of your final data model**. In Chapter 7, you will learn how to configure which queries load into the model and which ones stay behind as staging queries. For now, **save your .pbix file** but do not click Close & Apply.

> **File → Save** (or Ctrl + S). That is it. You are done with this worksheet.

---

## What This Prepares You For

Next week is **Lab #2: Combining Queries** (Week 11, 50 points). In that lab, you will:

- **Merge** the Sales table with Menu Items, Trucks, Employees, and Events using Left Joins
- **Configure loading** so only final tables load into the model
- **Verify row counts** to make sure no data was lost during merges

The Group By and Reference skills you practiced in Tasks 5–6 are directly relevant — you will create reference queries and configure which ones load. The text transformations from Tasks 1–3 gave you practice navigating between the Transform tab and the Add Column tab, which you will continue to use throughout the course.

**Review Chapter 7 before Monday.**

---

## Key Vocabulary from This Worksheet

| Term | What It Means |
|------|--------------|
| **Split Column** | Breaks one column into two or more columns using a delimiter (like a space or comma) |
| **Merge Columns** | Combines two or more columns into one column with a separator you choose |
| **Extract** | Pulls a specific piece of text from a column (first N characters, last N characters, etc.) |
| **Custom Column** | A new column created by writing a formula that calculates values from existing columns |
| **Group By** | Collapses many rows into summary rows based on a column, applying an aggregation (sum, average, count) |
| **Reference query** | A new query that points to the same data as an existing query without copying it — useful for creating summaries while keeping the original intact |
| **Transform tab** | Changes existing columns (replaces them) |
| **Add Column tab** | Creates new columns while keeping the originals |
| **Delimiter** | A character that marks where to split text (space, comma, tab, etc.) |
| **Aggregation** | A single value calculated from many values — sum, average, count, min, max |

---

> *Week 10 Practice Worksheet complete. Next: Chapter 7 — Combining Queries and Loading Data.*
