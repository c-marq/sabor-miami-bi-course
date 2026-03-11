# Tutoring Practice Lab: Cleaning a Cafe Sales Dataset

**CAP2791C: Power BI Data Preparation and Modeling | ND Section**  
**Tutoring Session — Ungraded Practice | 60 Minutes**  
**Skills Covered:** Weeks 9–10 (Cleaning, Transforming, Data Types, Group By, Visuals)

---

## 🚀 LAUNCH PAD

| | |
|---|---|
| **What you are building** | A cleaned cafe sales dataset with a custom column, a grouped summary, and 4 visuals |
| **Tool** | Power BI Desktop |
| **File to open** | `dirty_cafe_sales.csv` — [download from GitHub](https://github.com/c-marq/sabor-miami-bi-course/blob/main/datasets/dirty_cafe_sales.csv) |
| **Time estimate** | 55–60 minutes |
| **Number of phases** | 4 phases, 14 tasks total |
| **What "done" looks like** | One clean table with no errors, one calculated column, one grouped summary query, and a report page with 4 visuals |
| **Start here →** | Open Power BI Desktop and connect to the CSV file (Phase 1, Task 1) |

---

> **What is this dataset?** This is NOT Sabor Miami. This is a Kaggle dataset called "Cafe Sales — Dirty Data for Cleaning Training." It has 10,000 rows of synthetic cafe transactions — intentionally messy. You will use the same skills from Chapters 5 and 6 to clean it, transform it, and build visuals. Think of this as practice on a brand new dataset — exactly what a real analyst does when they get data they have never seen before.

---

## The Data at a Glance

Before you start, here is what the dataset contains:

| Column | What It Stores | Issues You Will Find |
|---|---|---|
| Transaction ID | Unique ID per sale (e.g., TXN_1961373) | Clean — no issues |
| Item | What was sold (Coffee, Cake, Sandwich, etc.) | Blanks, "ERROR", and "UNKNOWN" values |
| Quantity | How many units (1–5) | Stored as text, contains "ERROR" and "UNKNOWN" |
| Price Per Unit | Price of one unit ($1.00–$5.00) | Stored as text, contains "ERROR" and "UNKNOWN" |
| Total Spent | Quantity × Price Per Unit | Stored as text, contains "ERROR" and "UNKNOWN" |
| Payment Method | Cash, Credit Card, or Digital Wallet | ~2,500 blanks, plus "ERROR" and "UNKNOWN" |
| Location | In-store or Takeaway | ~3,200 blanks, plus "ERROR" and "UNKNOWN" |
| Transaction Date | Date of the sale (2023-01-01 to 2023-12-31) | Some blanks, "ERROR", and "UNKNOWN" |

**The big pattern:** This dataset uses "ERROR" and "UNKNOWN" as placeholder text in columns that should have real values. Your first job is to replace those with null so Power Query can treat them properly. Then you fix data types and clean up.

---

## Phase 1 of 4: Connect and Profile (8 minutes)

### Task 1 — Connect to the CSV File

<div style="background-color: #D5F5E3; border-left: 5px solid #27AE60; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #1E8449;">✅ DO THIS</strong><br>

**Step 1:** Download the dataset. Go to [https://github.com/c-marq/sabor-miami-bi-course/blob/main/datasets/dirty_cafe_sales.csv](https://github.com/c-marq/sabor-miami-bi-course/blob/main/datasets/dirty_cafe_sales.csv). Click the **download icon** (the arrow pointing down) in the top-right corner of the file preview, or click the **Raw** button and then right-click → **Save As** to save the file to your computer. Remember where you saved it.

**Step 2:** Open **Power BI Desktop**.

**Step 3:** Click **Get Data** on the Home tab → select **Text/CSV** → navigate to the `dirty_cafe_sales.csv` file you just downloaded → click **Open**.

**Step 4:** In the preview window, click **Transform Data** (not Load). This opens the Power Query Editor so you can clean before loading.

</div>

<div style="background-color: #FADBD8; border-left: 5px solid #E74C3C; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #922B21;">🛑 STOP AND CHECK</strong><br>
You should be in the <strong>Power Query Editor</strong> with one query (probably called "dirty_cafe_sales"). Look at the <strong>first row of data</strong> and the <strong>column headers</strong>.<br><br>
<strong>If the column headers say "Transaction ID", "Item", "Quantity", etc.</strong> — Power Query auto-promoted the first row as headers. You are good.<br><br>
<strong>If the column headers say "Column1", "Column2", "Column3", etc.</strong> — the first row of data contains the header names. Fix this now: go to the <strong>Home tab</strong> → click <strong>Use First Row as Headers</strong> (in the Transform section). The column names should update to "Transaction ID", "Item", "Quantity", and so on.<br><br>
Once your headers are correct, confirm you see 10,000 rows and 8 columns. Scroll through the first 20–30 rows — you should see "ERROR" and "UNKNOWN" scattered across several columns.
</div>

### Task 2 — Rename the Query

Right-click the query in the Queries pane → **Rename** → type: `Cafe Sales`

### Task 3 — Profile the Data

<div style="background-color: #D5F5E3; border-left: 5px solid #27AE60; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #1E8449;">✅ DO THIS</strong><br>

**Step 1:** Turn on profiling tools. Go to the **View tab** on the ribbon. Check all three boxes:
- ☑ Column Quality
- ☑ Column Distribution
- ☑ Column Profile

**Step 2:** Click "Column profiling based on entire data set" at the bottom of the status bar (by default it only profiles the first 1,000 rows — you want all 10,000).

</div>

<div style="background-color: #FADBD8; border-left: 5px solid #E74C3C; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #922B21;">🛑 STOP AND CHECK</strong><br>
Click the <strong>Payment Method</strong> column. Look at the Column Quality bar — you should see a large chunk of <strong>Empty</strong> values (roughly 25%). Click the <strong>Location</strong> column — even more empty values (roughly 32%). This is your first clue that the dataset has significant missing data.
</div>

<div style="background-color: #D6EAF8; border-left: 5px solid #2E86C1; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #1A5276;">💡 WHY ARE WE DOING THIS?</strong><br>
Profiling first is the pattern you learned in Week 8 — always look before you clean. In a real job, you would spend the first 15–30 minutes just understanding what is wrong before you fix anything. Today we are compressing that into a few minutes because you already know the tools.
</div>

---

## Phase 2 of 4: Clean (20 minutes)

### Task 4 — Replace "ERROR" and "UNKNOWN" with null

This is the biggest cleaning task. The dataset uses the text strings "ERROR" and "UNKNOWN" where values are missing. Power Query does not treat these as null — it treats them as valid text. You need to replace them so they become actual nulls.

<div style="background-color: #D5F5E3; border-left: 5px solid #27AE60; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #1E8449;">✅ DO THIS</strong><br>

You will run Replace Values **twice** — once for "ERROR" and once for "UNKNOWN". Do this on the **entire table**, not one column at a time.

**For "ERROR":**

**Step 1:** Click on any column header (it does not matter which one).

**Step 2:** Select all columns: press **Ctrl + A** (this selects every column in the table).

**Step 3:** Go to **Transform tab** → click **Replace Values**.

**Step 4:** In the Replace Values dialog:
- **Value to Find:** `ERROR`
- **Replace With:** *(leave this field completely empty)*
- Click **OK**.

**For "UNKNOWN":**

**Step 5:** With all columns still selected (press **Ctrl + A** again if needed), go to **Transform tab** → **Replace Values**.

**Step 6:** In the dialog:
- **Value to Find:** `UNKNOWN`
- **Replace With:** *(leave empty)*
- Click **OK**.

</div>

<div style="background-color: #FEF9E7; border-left: 5px solid #F1C40F; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #7D6608;">⚠️ COMMON MISTAKE</strong><br>
Make sure you type <strong>ERROR</strong> in all caps, exactly as it appears in the data. Replace Values is case-sensitive. Same for <strong>UNKNOWN</strong> — all caps.
</div>

<div style="background-color: #FADBD8; border-left: 5px solid #E74C3C; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #922B21;">🛑 STOP AND CHECK</strong><br>
Click the <strong>Item</strong> column. Column Distribution should now show 8 distinct items (Coffee, Cake, Cookie, Juice, Salad, Sandwich, Smoothie, Tea) plus some nulls. You should <strong>not</strong> see "ERROR" or "UNKNOWN" as categories anywhere in the data.<br><br>
Click through a few other columns — Quantity, Price Per Unit, Payment Method. The "ERROR" and "UNKNOWN" bars should be gone, replaced by null/empty values.
</div>

### Task 5 — Remove Rows Where Item is Null

Rows with no Item name cannot be analyzed — we do not know what was sold. Remove them.

<div style="background-color: #D5F5E3; border-left: 5px solid #27AE60; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #1E8449;">✅ DO THIS</strong><br>

**Step 1:** Click the **Item** column header.

**Step 2:** Click the **dropdown arrow** on the Item column header.

**Step 3:** Uncheck **(null)** (and **blank/empty** if it appears as a separate option). Leave all actual item names checked.

**Step 4:** Click **OK**.

</div>

<div style="background-color: #FADBD8; border-left: 5px solid #E74C3C; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #922B21;">🛑 STOP AND CHECK</strong><br>
Your row count (bottom-left corner of Power Query Editor) should have dropped. You started with 10,000 rows — after removing null Items, you should have roughly <strong>9,000–9,100 rows</strong>. The Item column should now show 100% Valid in Column Quality.
</div>

### Task 6 — Fix Data Types on Numerical Columns

The Quantity, Price Per Unit, and Total Spent columns are stored as text (ABC icon). They need to be numbers.

<div style="background-color: #D5F5E3; border-left: 5px solid #27AE60; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #1E8449;">✅ DO THIS</strong><br>

**Step 1:** Click the data type icon (ABC) to the left of the **Quantity** column header → select **Whole Number**.

**Step 2:** Click the data type icon to the left of **Price Per Unit** → select **Decimal Number**.

**Step 3:** Click the data type icon to the left of **Total Spent** → select **Decimal Number**.

**Step 4:** Check the **Transaction Date** column. If it shows ABC (Text), change it to **Date**.

</div>

<div style="background-color: #FEF9E7; border-left: 5px solid #F1C40F; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #7D6608;">⚠️ COMMON MISTAKE</strong><br>
If you see errors after changing a data type, it means some remaining values cannot be converted (for example, a blank cell trying to become a number). That is OK — Power Query converts what it can and marks the rest as errors. You can check Column Quality to see the error percentage.
</div>

<div style="background-color: #FADBD8; border-left: 5px solid #E74C3C; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #922B21;">🛑 STOP AND CHECK</strong><br>
The data type icons should now show:<br>
- Quantity: <strong>123</strong> (Whole Number)<br>
- Price Per Unit: <strong>1.2</strong> (Decimal Number)<br>
- Total Spent: <strong>1.2</strong> (Decimal Number)<br>
- Transaction Date: <strong>📅</strong> (Date)<br>
- Everything else stays as <strong>ABC</strong> (Text)
</div>

### Task 7 — Replace Null Payment Methods and Locations with "Unknown"

Payment Method and Location have a lot of blanks. Rather than deleting these rows (we would lose too much data), replace the nulls with the text "Unknown" so they still appear in visuals.

<div style="background-color: #D5F5E3; border-left: 5px solid #27AE60; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #1E8449;">✅ DO THIS</strong><br>

**Step 1:** Click the **Payment Method** column header.

**Step 2:** Go to **Transform tab** → **Replace Values**.
- **Value to Find:** `null`
- **Replace With:** `Unknown`
- Click **OK**.

**Step 3:** Repeat for the **Location** column:
- Click **Location** column header → Transform tab → Replace Values
- **Value to Find:** `null`
- **Replace With:** `Unknown`
- Click **OK**.

</div>

<div style="background-color: #D6EAF8; border-left: 5px solid #2E86C1; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #1A5276;">💡 WHY ARE WE DOING THIS?</strong><br>
This is the same decision-making you practiced in Lab #1 with Sabor Miami. Null tip amounts got replaced with 0 (because no tip means zero dollars). Null phone numbers stayed as null (because we cannot invent a phone number). Here, we replace null Payment Method and Location with "Unknown" because we want these rows in our visuals — we just do not know the payment type or location. Deleting 3,000+ rows would throw away too much data.
</div>

<div style="background-color: #FADBD8; border-left: 5px solid #E74C3C; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #922B21;">🛑 STOP AND CHECK</strong><br>
Click the <strong>Payment Method</strong> column. Column Distribution should show 4 categories: Cash, Credit Card, Digital Wallet, and Unknown. No more blanks or nulls.<br><br>
Click the <strong>Location</strong> column. It should show 3 categories: In-store, Takeaway, and Unknown.
</div>

---

<div style="background-color: #E8DAEF; border-left: 5px solid #8E44AD; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #6C3483;">💜 TAKE A BREATH</strong><br>
The hard part is done. You just cleaned a dataset that was not Sabor Miami — that means you can transfer these skills to any messy data you encounter. The remaining phases are faster: one transformation, one Group By, then visuals.
</div>

---

## Phase 3 of 4: Transform (10 minutes)

### Task 8 — Create a Custom Column: Calculated Total

The dataset has a Total Spent column, but some values are null (from the ERROR/UNKNOWN cleanup). You can recalculate any missing totals using Quantity × Price Per Unit.

<div style="background-color: #D5F5E3; border-left: 5px solid #27AE60; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #1E8449;">✅ DO THIS</strong><br>

**Step 1:** Go to the **Add Column tab** on the ribbon.

**Step 2:** Click **Custom Column**.

**Step 3:** In the Custom Column dialog:
- **New column name:** `Calculated Total`
- **Custom column formula:** `[Quantity] * [Price Per Unit]`
- Click **OK**.

</div>

<div style="background-color: #FADBD8; border-left: 5px solid #E74C3C; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #922B21;">🛑 STOP AND CHECK</strong><br>
Scroll right to find the new <strong>Calculated Total</strong> column. Spot-check: if Quantity = 2 and Price Per Unit = 3.00, Calculated Total should be 6.00. Some rows will show <strong>null</strong> in Calculated Total — that happens when Quantity or Price Per Unit is null. That is expected.
</div>

### Task 9 — Create a Grouped Summary: Sales By Item

<div style="background-color: #D5F5E3; border-left: 5px solid #27AE60; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #1E8449;">✅ DO THIS</strong><br>

**Step 1:** In the Queries pane, right-click the **Cafe Sales** query → select **Reference**.

**Step 2:** Rename the new query to: `Sales By Item`

**Step 3:** With the Sales By Item query selected, click **Group By** (Transform tab → Table section).

**Step 4:** In the Group By dialog, click **Advanced**. Configure:

**Group by:** `Item`

**First aggregation:**
- **New column name:** `Total Revenue`
- **Operation:** `Sum`
- **Column:** `Calculated Total`

Click **Add aggregation**.

**Second aggregation:**
- **New column name:** `Transaction Count`
- **Operation:** `Count Rows`

Click **OK**.

</div>

<div style="background-color: #FADBD8; border-left: 5px solid #E74C3C; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #922B21;">🛑 STOP AND CHECK</strong><br>
The Sales By Item query should show <strong>8 rows</strong> — one for each item (Cake, Coffee, Cookie, Juice, Salad, Sandwich, Smoothie, Tea). Each row has the Item name, Total Revenue, and Transaction Count. Salad and Sandwich should have higher Total Revenue values (they cost more per unit). Coffee and Cookie should have higher Transaction Counts (they are ordered more frequently).
</div>

### Task 10 — Close & Apply

<div style="background-color: #D5F5E3; border-left: 5px solid #27AE60; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #1E8449;">✅ DO THIS</strong><br>

**Step 1:** Click **Close & Apply** on the Home tab of the Power Query Editor (top-left corner). This loads your cleaned data into the Power BI data model.

**Step 2:** Wait for the loading to finish. You will return to the main Power BI Desktop window (Report View with the blank canvas).

</div>

---

## Phase 4 of 4: Build Visuals (15 minutes)

Now that your data is loaded, build 4 visuals on the report canvas. Each visual uses a different chart type so you get practice with the Visualizations pane.

**WHERE AM I?** You should be in **Report View** — the main Power BI Desktop window with the blank canvas, the Visualizations pane on the right, and the Data pane showing your fields.

### Task 11 — Bar Chart: Total Revenue by Item

<div style="background-color: #D5F5E3; border-left: 5px solid #27AE60; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #1E8449;">✅ DO THIS</strong><br>

**Step 1:** Click on the blank canvas to make sure nothing is selected.

**Step 2:** In the Visualizations pane (right side), click the **Clustered Bar Chart** icon (horizontal bars).

**Step 3:** From the **Data pane**, drag these fields:
- Drag **Item** (from the Cafe Sales table) into the **Y-axis** well
- Drag **Calculated Total** into the **X-axis** well

**Step 4:** Power BI will automatically sum the Calculated Total values. You should see 8 bars — one per item — sorted by revenue.

**Step 5:** Resize the visual to take up roughly the **top-left quarter** of the canvas.

</div>

### Task 12 — Donut Chart: Transactions by Payment Method

<div style="background-color: #D5F5E3; border-left: 5px solid #27AE60; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #1E8449;">✅ DO THIS</strong><br>

**Step 1:** Click on a blank area of the canvas (not on the bar chart).

**Step 2:** In the Visualizations pane, click the **Donut Chart** icon.

**Step 3:** Drag these fields:
- Drag **Payment Method** into the **Legend** well
- Drag **Transaction ID** into the **Values** well (Power BI will count them automatically)

**Step 4:** Position this visual in the **top-right quarter** of the canvas.

</div>

### Task 13 — Line Chart: Sales Over Time

<div style="background-color: #D5F5E3; border-left: 5px solid #27AE60; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #1E8449;">✅ DO THIS</strong><br>

**Step 1:** Click on a blank area of the canvas.

**Step 2:** In the Visualizations pane, click the **Line Chart** icon.

**Step 3:** Drag these fields:
- Drag **Transaction Date** into the **X-axis** well
- Drag **Calculated Total** into the **Y-axis** well

**Step 4:** Power BI may automatically create a date hierarchy (Year → Quarter → Month → Day). If it does, click the **drill-down arrows** at the top of the visual to explore different levels, or click the small **"X"** next to "Year" in the X-axis well to switch to the raw date values.

**Step 5:** Position this visual in the **bottom-left quarter** of the canvas.

</div>

### Task 14 — Card: Total Transaction Count

<div style="background-color: #D5F5E3; border-left: 5px solid #27AE60; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #1E8449;">✅ DO THIS</strong><br>

**Step 1:** Click on a blank area of the canvas.

**Step 2:** In the Visualizations pane, click the **Card** icon (a single large number display).

**Step 3:** Drag **Transaction ID** into the **Fields** well. Power BI will default to "Count" — which gives you the total number of transactions.

**Step 4:** Position this visual in the **bottom-right area** of the canvas.

</div>

<div style="background-color: #FADBD8; border-left: 5px solid #E74C3C; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #922B21;">🛑 STOP AND CHECK — ALL VISUALS</strong><br>
Your report page should now have 4 visuals:<br><br>
1. <strong>Bar chart</strong> (top-left) — shows revenue by item. Salad and Sandwich should be near the top.<br>
2. <strong>Donut chart</strong> (top-right) — shows transaction distribution by payment method. Cash, Credit Card, Digital Wallet should be roughly equal, with an "Unknown" slice.<br>
3. <strong>Line chart</strong> (bottom-left) — shows sales trend across 2023.<br>
4. <strong>Card</strong> (bottom-right) — shows total number of transactions (should be somewhere around 9,000).<br><br>
Click on a bar in the bar chart. Watch the other visuals filter. That is <strong>cross-filtering</strong> — Power BI's visuals talk to each other automatically.
</div>

---

<div style="background-color: #E8DAEF; border-left: 5px solid #8E44AD; padding: 15px; margin: 15px 0; border-radius: 4px;">
<strong style="color: #6C3483;">💜 TAKE A BREATH</strong><br>
You just took a messy Kaggle dataset with 10,000 rows, cleaned it using Power Query, created a calculated column and a grouped summary, and built 4 visuals — all in under an hour. This is the full pipeline: <strong>Get → Profile → Clean → Transform → Visualize</strong>. That is what data analysts do every day.
</div>

---

## Save Your Work

**File → Save As → `LastName_FirstName_CafeSales_Practice.pbix`**

This file is for your reference only — it is not graded and does not need to be submitted.

---

## What You Practiced Today

| Week | Skill | Where You Used It |
|---|---|---|
| Week 9 (Ch 5) | Replace Values | Task 4 — replacing ERROR and UNKNOWN with null |
| Week 9 (Ch 5) | Remove Rows | Task 5 — filtering out null Items |
| Week 9 (Ch 5) | Change Data Types | Task 6 — fixing Quantity, Price, Total Spent, Date |
| Week 9 (Ch 5) | Null Handling Decisions | Task 7 — replacing null Payment Method/Location with "Unknown" |
| Week 10 (Ch 6) | Custom Column | Task 8 — Calculated Total = Quantity × Price Per Unit |
| Week 10 (Ch 6) | Group By (Advanced) | Task 9 — Sales By Item with Sum and Count Rows |
| Week 10 (Ch 6) | Reference Query | Task 9 — creating a reference before grouping |
| New Preview | Building Visuals | Tasks 11–14 — bar chart, donut chart, line chart, card |

---

> *Tutoring Practice Lab complete. Next class: Chapter 7 — Combining Queries and Loading Data.*
