# Week 9 Practice: Cleaning Real Data

**CAP2791C — Power BI: Data Preparation and Modeling**
**Self-Guided Tutoring Exercise | Available All Week**

---

> **What is this?** This is an extra practice exercise using real Miami-Dade County restaurant inspection data. It is **not graded**. It uses the same cleaning tools you learned in Session 9A — Replace Values, Proper Case, Trim, data type changes, and renaming. If you can finish this exercise, you are ready for Lab #1.

---

## 🚀 LAUNCH PAD

| | |
|---|---|
| **What you're building** | A cleaned version of a Miami-Dade restaurant inspection dataset |
| **Tool** | Power BI Desktop |
| **File to open** | [`MiamiDade_Restaurant_Inspections_Practice.csv`](https://github.com/c-marq/sabor-miami-bi-course/blob/main/datasets/MiamiDade_Restaurant_Inspections_Practice.csv) (download from GitHub) |
| **Time estimate** | 30–45 minutes |
| **Steps** | 7 |
| **What "done" looks like** | A .pbix file with one clean query, proper column names, consistent text, and correct data types |
| **Start here →** | Open Power BI Desktop and click **Get Data** |

---

## Where Did This Data Come From?

This data comes from the Florida Department of Business and Professional Regulation (DBPR). They inspect every restaurant in the state and publish the results online. The file you are working with contains **50 real restaurant inspections from Miami-Dade County** in 2025–2026.

You may recognize some of these restaurants — Versailles, Joe's Stone Crabs, Pollo Tropical, La Carreta. This is real public data. It is also real-world messy.

---

## Step 1: Load the Data into Power BI

1. Open **Power BI Desktop**
2. Click **Get Data** on the Home screen (or **Home tab → Get Data**)
3. Select **Text/CSV**
4. Browse to `MiamiDade_Restaurant_Inspections_Practice.csv` and click **Open**
5. A preview window appears. Look at the data — don't click Load yet
6. Click **Transform Data** to open Power Query Editor

> 🛑 **STOP AND CHECK**
> You should now be in Power Query Editor. You should see one query on the left called `MiamiDade_Restaurant_Inspections_Practice` and a table with 50 rows and 11 columns.

---

## Step 2: Profile the Data

Before you fix anything, look at what needs fixing. Turn on profiling tools:

1. Go to the **View** tab in Power Query Editor
2. Check all three boxes: **Column quality**, **Column distribution**, **Column profile**
3. At the bottom left, make sure it says **Column profiling based on entire data set** — if it says "Top 1000 rows," click it to change it

Now scroll through each column. You are looking for:

- Error values (shown in red on the quality bar)
- Empty values (shown in gray on the quality bar)
- Inconsistent text (look at the distinct values and unique values counts)

> 💡 **WHY ARE WE DOING THIS?**
> This is the same profiling you did in Week 8 with the Sabor Miami dataset. The difference is that this data is real — nobody seeded these issues on purpose. Real data is messy because real people enter it.

**Write down at least 5 issues you notice.** You can use paper, a notes app, or just keep a mental list. You'll fix them in the next steps.

---

## Step 3: Fix the Column Header

Look at the second column. Its name has a leading space: ` Location Address` instead of `Location Address`.

1. **Double-click** the column header ` Location Address`
2. Delete the space at the beginning
3. Type `Location Address` and press **Enter**

Check the Applied Steps panel on the right — you should see a new step called "Renamed Columns."

> ⚠️ **COMMON MISTAKE**
> If you accidentally rename the wrong column, click the **X** next to the step in Applied Steps to undo it. Don't try to rename it again — that creates two rename steps and gets confusing.

---

## Step 4: Fix Text Casing

Several columns have inconsistent casing. Let's fix them one at a time.

**Business Name — Apply Proper Case:**

The business names are mostly ALL CAPS. There is also one in all lowercase (`night owl cookies`). Proper Case fixes both.

1. Click the **Business Name** column header to select it
2. Go to the **Transform** tab in the ribbon
3. Click **Format** → **Capitalize Each Word**

Scroll through the results. You should see "The Abbey Hotel" instead of "THE ABBEY HOTEL" and "Night Owl Cookies" instead of "night owl cookies."

**Location City — Apply Proper Case:**

Some cities are ALL CAPS ("MIAMI"), some are lowercase ("miami").

1. Click the **Location City** column header
2. **Transform tab → Format → Capitalize Each Word**

**Inspection Type — Apply Proper Case:**

Most values say "Routine - Food" but a few say "routine - food."

1. Click the **Inspection Type** column header
2. **Transform tab → Format → Capitalize Each Word**

**Inspection Result — Apply Proper Case:**

Most values say "Warning Issued" but a few say "warning issued."

1. Click the **Inspection Result** column header
2. **Transform tab → Format → Capitalize Each Word**

> 🛑 **STOP AND CHECK**
> Check your Applied Steps panel — you should now have 4 new "Capitalized Each Word" steps (one per column). Scroll through the data to confirm the casing looks consistent.

---

## 💜 TAKE A BREATH

You just cleaned text casing across four columns. That is real data cleaning — the kind analysts do on every new dataset. Stretch, get some water, check your phone for a minute. The next steps build on what you just did.

---

## Step 5: Fix Text Issues with Replace Values and Trim

**Remove trailing spaces:**

Some business names and addresses have invisible extra spaces at the end. You can't see them, but Power BI can — and they cause matching errors later.

1. Click the **Business Name** column header
2. Go to the **Transform** tab → **Format** → **Trim**
3. Repeat for the **Location Address** column: click it, then **Transform tab → Format → Trim**

**Fix the extra space in an address:**

The address "811 W  49 St" has two spaces between "W" and "49." Trim doesn't fix spaces in the middle of text — only at the edges. Use Replace Values for this.

1. Click the **Location Address** column header
2. Go to **Home tab → Replace Values**
3. In "Value to Find," type two spaces (press the spacebar twice)
4. In "Replace With," type one space (press the spacebar once)
5. Click **OK**

**Fix the restaurant name inconsistency:**

There are two entries for the same restaurant at 7535 SW 8th St — one says "Taquerias El Mexicano" and the other says "Taqueria El Mexicano." Let's standardize to the correct name.

1. Click the **Business Name** column header
2. **Home tab → Replace Values**
3. Value to Find: `Taquerias El Mexicano`
4. Replace With: `Taqueria El Mexicano`
5. Click **OK**

---

## Step 6: Fix Data Types

**Remove the dollar sign from Total Violations:**

One row has `$3` instead of `3` in the Total Violations column. This prevents Power BI from treating the column as a number.

1. Click the **Total Violations** column header
2. **Home tab → Replace Values**
3. Value to Find: `$`
4. Replace With: (leave this empty — delete everything in the box)
5. Click **OK**

Now change the data type:

6. With Total Violations still selected, look at the left side of the **Transform** tab for the **Data Type** dropdown
7. Change it from **Text** to **Whole Number**

> ⚠️ **COMMON MISTAKE**
> If you try to change the data type BEFORE removing the `$`, Power BI will show errors. Always clean the content first, then change the type. This is the same order-of-operations lesson from Chapter 5.

**Repeat for the other violation columns:**

The columns **High Priority**, **Intermediate**, and **Basic** should also be Whole Number. Check their data type — if they show as Text, change them to Whole Number.

1. Click **High Priority** → **Transform tab → Data Type → Whole Number**
2. If Power BI asks about replacing the existing conversion, click **Replace current**
3. Repeat for **Intermediate** and **Basic**

> 🛑 **STOP AND CHECK**
> All four violation columns (Total Violations, High Priority, Intermediate, Basic) should now show the number icon (123) in their column headers instead of the text icon (ABC).

---

## Step 7: Rename the Query

The query name in the left panel is still the long file name. Let's clean it up.

1. In the **Queries** panel on the left, **right-click** the query name
2. Select **Rename**
3. Type `Restaurant Inspections` and press **Enter**

Now apply your changes:

4. Click **Close & Apply** (Home tab, far left)
5. **Save** your file as `Week9_Practice_YourName.pbix`

---

## ✅ You're Done

Here's what you just practiced:

| Skill | What You Did |
|-------|-------------|
| **Profiling** | Used Column quality, distribution, and profile to scan for issues |
| **Rename** | Fixed a column header with a leading space, renamed the query |
| **Proper Case** | Standardized text casing across 4 columns |
| **Trim** | Removed trailing spaces from 2 columns |
| **Replace Values** | Fixed a double space, a name inconsistency, and removed a `$` from a number |
| **Data Type** | Changed 4 columns from Text to Whole Number (after cleaning content first) |

These are the same tools you'll use in Thursday's Lab #1 on the Sabor Miami dataset. The tasks will be different, but the techniques are the same.

---

## 🔍 Bonus Challenges (Optional)

If you finished early and want extra practice, try these. They are NOT required.

1. **Mixed date formats:** The Inspection Date column has most dates as `MM/DD/YYYY` but a couple use `MM-DD-YYYY` with dashes instead of slashes. Can you use Replace Values to standardize the dashes to slashes, then change the column to a Date data type?

2. **Inconsistent ZIP codes:** The Location Zip column has values like `33139`, `331435003`, `33143-3645`, and one blank. What would you do with each? Think about it — there is no single right answer. This is a judgment call, just like the null phone numbers vs. null tips discussion from class.

3. **Empty violation counts:** Row 24 (Casa Juancho) has empty violation counts. Should you replace those with 0 or leave them as empty? What's the difference? (Hint: an empty value might mean "not recorded" while 0 means "zero violations found.")

---

## Where to Get Help

- Re-read **Chapter 5** on GitHub
- Review your notes from **Session 9A**
- Check the **Applied Steps** panel if you get lost — you can always delete a step by clicking the X next to it

---

> **Source:** This practice data is adapted from public restaurant inspection records published by the Florida Department of Business and Professional Regulation (DBPR) at [myfloridalicense.com](https://www2.myfloridalicense.com/hotels-restaurants/public-records/). Data is from Miami-Dade County, FY 2025–2026.
