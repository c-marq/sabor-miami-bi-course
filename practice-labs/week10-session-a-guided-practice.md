# Week 10 Session A: Guided Practice — Transforming Data Step by Step

**CAP2791C: Power BI Data Preparation and Modeling | ND Section**  
**Week 10 Monday | Follow Along with Your Instructor**  
**Chapter 6 Skills: Split, Merge, Custom Column, Group By**

---

## 🚀 LAUNCH PAD

| | |
|---|---|
| **What you are building** | Four transformations on the Sabor Miami dataset, following along with your instructor |
| **Tool** | Power BI Desktop → Power Query Editor |
| **File to open** | A **practice copy** of your cleaned Lab #1 .pbix file (you will Save As first — see Step 0) |
| **Time estimate** | 20–25 minutes |
| **Number of activities** | 4 follow-along activities |
| **What "done" looks like** | Employees table has split name columns and a Display Name. Sales has a Total With Tip column. You have seen Group By collapse rows and then undone it. |
| **Start here →** | Open your Lab #1 .pbix file and immediately **Save As** a practice copy (Step 0) |

---

> **How this works:** Your instructor will do each step on the projector. You do the same step on your screen. Do not move ahead — wait for each step to be called out. If you fall behind, raise your hand and your instructor will come to your screen.

---

## Step 0: Create Your Practice Copy

We are going to make changes to the data today that you do **not** want saved into your Lab #1 file. Your clean Lab #1 file is the starting point for Lab #2 next week, so we need to protect it.

<div style="background-color: #D5F5E3; border-left: 5px solid #27AE60; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #1E8449;">✅ DO THIS</strong><br>

**Step 1:** Open your cleaned Lab #1 .pbix file in Power BI Desktop.

**Step 2:** Go to **File → Save As**.

**Step 3:** Save it with a new name: `LastName_FirstName_Week10_GuidedPractice.pbix`

**Step 4:** Check the title bar at the top of Power BI Desktop. It should show your new practice file name — **not** your Lab #1 file name.

**Step 5:** Click **Transform Data** on the Home tab to open the Power Query Editor.

</div>

<div style="background-color: #FADBD8; border-left: 5px solid #E74C3C; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #922B21;">🛑 STOP AND CHECK</strong><br>
You should be in the <strong>Power Query Editor</strong> — the separate window with the green ribbon. The Queries pane on the left should show your five cleaned queries: <strong>Sales, Menu Items, Trucks, Employees, Events</strong>.<br><br>
<strong>Wait here. Do not move ahead until your instructor says "Ready? Let's go."</strong>
</div>

---

## Activity 1 of 4: Split a Column (Employees Table)

**What we are doing:** Taking the employee name column and splitting it into two columns — First Name and Last Name.

**Why:** Sometimes data arrives with values combined in a single column that you need to separate. Split Column by Delimiter is how you break one column into pieces.

<div style="background-color: #D5F5E3; border-left: 5px solid #27AE60; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #1E8449;">✅ FOLLOW ALONG</strong><br>

**Step 1:** In the Queries pane on the left, click the **Employees** query.

**Step 2:** Find the column that contains employee full names (it may be called Full Name, Employee Name, or Name). Click the **column header** to select it.

**Step 3:** Go to the **Transform tab** on the ribbon.

**Step 4:** Click the **Split Column** button — it is in the **Text Column** section, toward the right side of the ribbon. Select **By Delimiter**.

**Step 5:** In the dialog:
- **Delimiter:** Select **Space**.
- **Split at:** Select **At the left-most delimiter**.
- Click **OK**.

**Step 6:** The column splits into two. Rename them:
- Double-click the first new column header → type `First Name`
- Double-click the second new column header → type `Last Name`

</div>

<div style="background-color: #FADBD8; border-left: 5px solid #E74C3C; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #922B21;">🛑 STOP AND CHECK</strong><br>
Your Employees table should now have <strong>First Name</strong> and <strong>Last Name</strong> as separate columns. Scan a few rows — first names in one column, last names in the other. The original combined name column should be gone.<br><br>
Check the <strong>Applied Steps</strong> pane on the right. You should see new steps: "Split Column by Delimiter" and "Renamed Columns."<br><br>
<strong>Does your screen match the projector? If yes, thumbs up. If not, raise your hand.</strong>
</div>

<div style="background-color: #D6EAF8; border-left: 5px solid #2E86C1; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #1A5276;">💡 WHY ARE WE DOING THIS?</strong><br>
Split Column is one of the most common text transformations in real data work. Names, addresses, product codes — anytime someone combined two pieces of information into one column, Split Column by Delimiter is how you separate them. The <strong>delimiter</strong> is just the character that marks where to cut (a space, a comma, a dash).
</div>

---

## Activity 2 of 4: Merge Columns into Display Name (Employees Table)

**What we are doing:** Combining First Name and Last Name back together, but in a new format — "Last, First" — to create a Display Name column. We will keep the original columns.

**Why:** The same data can serve different purposes depending on its shape. An alphabetical employee list needs "Last, First" format. A name badge needs just the first name. Merge Columns lets you create the format you need.

<div style="background-color: #D6EAF8; border-left: 5px solid #2E86C1; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #1A5276;">💡 IMPORTANT DISTINCTION</strong><br>
The <strong>Transform tab</strong> and the <strong>Add Column tab</strong> often have the same buttons — but they do different things.<br><br>
<strong>Transform tab</strong> = changes existing columns (replaces them).<br>
<strong>Add Column tab</strong> = creates a new column while keeping the originals.<br><br>
We want to <strong>keep</strong> First Name and Last Name AND create a new Display Name column. So we use the <strong>Add Column tab</strong>.
</div>

<div style="background-color: #D5F5E3; border-left: 5px solid #27AE60; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #1E8449;">✅ FOLLOW ALONG</strong><br>

**Step 1:** Click the **Last Name** column header. Then hold **Ctrl** and click the **First Name** column header. Both columns should be highlighted.

**Step 2:** Go to the **Add Column tab** on the ribbon — **not** the Transform tab.

**Step 3:** Click the **Merge Columns** button — it is in the **Text** section of the Add Column ribbon.

**Step 4:** In the Merge Columns dialog:
- **Separator:** Select **Custom**.
- **Custom separator:** Type a comma followed by a space: `, `
- **New column name:** Type `Display Name`
- Click **OK**.

</div>

<div style="background-color: #FADBD8; border-left: 5px solid #E74C3C; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #922B21;">🛑 STOP AND CHECK</strong><br>
You should see <strong>three</strong> name-related columns in Employees: <strong>First Name</strong>, <strong>Last Name</strong>, and <strong>Display Name</strong>. Display Name values should look like "Santos, Maria" or "Delgado, Jorge".<br><br>
<strong>If First Name and Last Name disappeared</strong>, you accidentally used the Transform tab. Click the <strong>X</strong> next to the last step in Applied Steps to undo, and try again using the <strong>Add Column tab</strong>.<br><br>
<strong>Does your screen match the projector?</strong>
</div>

---

<div style="background-color: #E8DAEF; border-left: 5px solid #8E44AD; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #6C3483;">💜 TAKE A BREATH</strong><br>
Two down, two to go. You just did the two core text transformations: Split took one column apart, Merge put columns back together in a new format. Quick stretch if you need it. Next we switch to the Sales table and work with numbers.
</div>

---

## Activity 3 of 4: Create a Custom Calculated Column (Sales Table)

**What we are doing:** Adding a new column to Sales that calculates the total each customer paid, including the tip: Amount + Tip.

**Why:** The raw data stores Amount and Tip in separate columns. For business reporting, people often want to see the total transaction value. A Custom Column lets you calculate new values from existing columns.

<div style="background-color: #D5F5E3; border-left: 5px solid #27AE60; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #1E8449;">✅ FOLLOW ALONG</strong><br>

**Step 1:** In the Queries pane on the left, click the **Sales** query.

**Step 2:** Before we create the column, let us confirm our data types. Look at the icons to the left of the **Amount** and **Tip** column headers:
- **1.2** or **$** = numerical (good)
- **ABC** = text (needs fixing first)

**Step 3:** Go to the **Add Column tab** on the ribbon.

**Step 4:** Click the **Custom Column** button — it is in the **General** section on the left side of the ribbon.

**Step 5:** In the Custom Column dialog:
- **New column name:** Type `Total With Tip`
- **Custom column formula:** Type `[Amount] + [Tip]`
- Column names go inside square brackets. You can also double-click a column name in the "Available columns" list on the right to insert it.
- Click **OK**.

</div>

<div style="background-color: #FADBD8; border-left: 5px solid #E74C3C; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #922B21;">🛑 STOP AND CHECK</strong><br>
Scroll to the right side of the Sales table. You should see a new column called <strong>Total With Tip</strong>.<br><br>
<strong>Spot-check:</strong> Pick any row. Look at the Amount and Tip values. Add them together mentally. Does the Total With Tip value match? For example: Amount = 15.00, Tip = 2.00 → Total With Tip should be 17.00.<br><br>
If you see <strong>Error</strong> in any rows, the most likely cause is null Tip values. In Lab #1, you should have replaced null tips with 0. If that step was missed, ask your instructor.
</div>

<div style="background-color: #D6EAF8; border-left: 5px solid #2E86C1; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #1A5276;">💡 WHY ARE WE DOING THIS?</strong><br>
Custom Column is how you add calculated fields in Power Query. The formula syntax uses <strong>square brackets</strong> around column names: <code>[Amount] + [Tip]</code>. This is different from Excel formulas (which use cell references like A2 + B2) and different from DAX (which you will learn in Week 13). Three tools, three formula styles — but the concept of "new value from existing values" is the same.
</div>

---

## Activity 4 of 4: Group By — See It, Then Undo It (Sales Table)

**What we are doing:** Using Group By to collapse the entire Sales table into a summary — total sales per truck. Then we will **undo it** to get the detail rows back.

**Why:** Group By is the Power Query version of SQL's `GROUP BY`. It is one of the most powerful transformations in this chapter. But it replaces the table — all the detail rows disappear and you get a summary. That is why we are going to run it, see what it does, and then remove the step.

<div style="background-color: #D6EAF8; border-left: 5px solid #2E86C1; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #1A5276;">💡 SQL CONNECTION</strong><br>
In your database course (Course 2), you wrote queries like:<br><br>
<code>SELECT Truck_ID, SUM(Amount) AS Total_Sales FROM Sales GROUP BY Truck_ID;</code><br><br>
Power Query's Group By button does the same thing — visually. You pick the column to group on, choose an aggregation (sum, average, count), and it produces the summary. Same logic, different interface.
</div>

### Part A: Run the Group By

<div style="background-color: #D5F5E3; border-left: 5px solid #27AE60; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #1E8449;">✅ FOLLOW ALONG</strong><br>

**Step 1:** Make sure you are still on the **Sales** query.

**Step 2:** Before grouping, note the current **row count**. Look at the bottom-left corner of the Power Query Editor — it shows something like "X rows loaded." Write this number down or remember it.

> **My Sales row count before grouping:** ____________

**Step 3:** Click the **Group By** button.
- **Find It:** It is in the **Transform tab**, in the **Table** section on the left side of the ribbon.

**Step 4:** In the Group By dialog (make sure **Basic** is selected):
- **Group by:** `Truck ID`
- **New column name:** `Total Sales`
- **Operation:** `Sum`
- **Column:** `Amount`
- Click **OK**.

</div>

<div style="background-color: #FADBD8; border-left: 5px solid #E74C3C; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #922B21;">🛑 STOP AND CHECK</strong><br>
Look at what just happened:<br><br>
<strong>Before:</strong> Your Sales table had hundreds (or thousands) of detail rows — one row per transaction.<br>
<strong>After:</strong> Your Sales table now has exactly <strong>4 rows</strong> — one for each truck (T001, T002, T003, T004). Each row shows a Truck ID and the Total Sales for that truck.<br><br>
All the individual transaction detail is gone. It was replaced by the summary. This is what Group By does — it collapses rows.
</div>

### Part B: Undo the Group By

<div style="background-color: #FEF9E7; border-left: 5px solid #F1C40F; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #7D6608;">⚠️ KEY LESSON</strong><br>
Group By <strong>replaces</strong> the table with a summary. If you run Group By on your Sales query, you lose all the detail rows. In Thursday's practice worksheet, you will learn how to use a <strong>Reference query</strong> to group a copy while keeping the original intact. For now, we are going to undo this step.
</div>

<div style="background-color: #D5F5E3; border-left: 5px solid #27AE60; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #1E8449;">✅ FOLLOW ALONG</strong><br>

**Step 1:** Look at the **Applied Steps** pane on the right side of the Power Query Editor.

**Step 2:** Find the last step — it should be called **Grouped Rows**.

**Step 3:** Click the **X** to the left of the "Grouped Rows" step to delete it.

**Step 4:** Your full Sales table should reappear with all the original detail rows.

</div>

<div style="background-color: #FADBD8; border-left: 5px solid #E74C3C; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #922B21;">🛑 STOP AND CHECK</strong><br>
Your Sales table should be back to its full size. Check the row count at the bottom-left corner — it should match the number you wrote down before grouping.<br><br>
<strong>The Group By step should be gone from Applied Steps.</strong> Your Sales query is back to normal.
</div>

---

<div style="background-color: #E8DAEF; border-left: 5px solid #8E44AD; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #6C3483;">💜 TAKE A BREATH</strong><br>
That is the guided practice. You just did four transformations that represent the core of Chapter 6:<br><br>
<strong>Split Column</strong> — broke a name into First and Last<br>
<strong>Merge Columns</strong> — combined them into Display Name (using Add Column tab to keep the originals)<br>
<strong>Custom Column</strong> — calculated Total With Tip from Amount + Tip<br>
<strong>Group By</strong> — collapsed Sales into a per-truck summary, then undid it<br><br>
On Thursday, you will practice these same skills independently — plus a couple of new variations — using a practice worksheet. Save your file if you want to keep it for reference, or just close it. Your Lab #1 file is untouched.
</div>

---

## Quick Reference: What You Learned Today

| Skill | Where to Find It | What It Does |
|---|---|---|
| **Split Column** | Transform tab → Text Column section → Split Column → By Delimiter | Breaks one column into multiple columns at a character you choose |
| **Merge Columns** | **Add Column tab** → Text section → Merge Columns | Combines columns into a new column with a separator (keeps originals) |
| **Merge Columns** | **Transform tab** → Text Column section → Merge Columns | Combines columns and **replaces** the originals (be careful) |
| **Custom Column** | Add Column tab → General section → Custom Column | Creates a new column using a formula like `[Amount] + [Tip]` |
| **Group By** | Transform tab → Table section → Group By | Collapses rows into a summary (sum, average, count). **Replaces the table.** |

---

## What Is Coming Thursday

Thursday's practice worksheet covers the same four skill categories, but you will work **independently** from written instructions. It also adds two new things:

- **Extract** — pulling specific characters from a column (like the first letter of Truck ID)
- **Reference queries** — creating a copy of a query so you can Group By without destroying the original

These skills connect directly to Lab #2 in Week 11.

---

> *Week 10 Session A Guided Practice complete. Thursday: Practice Worksheet (independent, 6 tasks).*
