# Comprehension Check #1: Weeks 1-7 Review
# COMPREHENSION CHECK #1 — Weeks 1-7 Review
## CAP2791C: Power BI Data Preparation and Modeling (ND Section)

**Canvas Settings:**
- Points: 10 (2 points each)
- Time Limit: NONE
- Attempts: 3 (highest score kept)
- Feedback: Show correct answer + explanation after each attempt
- Availability: Open from Week 8 Session B through end of Week 9

---

### Question 1 (Connecting to Data)

**When you connect Power BI to an Excel file on your computer, Power BI gives you two main options for how it handles the data: Import and DirectQuery. Which statement below is TRUE about Import mode?**

A) Import mode keeps a live connection to the Excel file, so any changes in Excel immediately appear in Power BI  
B) Import mode copies the data INTO your Power BI file, so you can work with it even if the original Excel file is moved or deleted  
C) Import mode requires an internet connection at all times  
D) Import mode is only available for database sources, not Excel files  

**Correct Answer: B**

**Feedback for incorrect answers:**
- If A: That describes DirectQuery, not Import. Import copies the data into your .pbix file. DirectQuery keeps a live connection.
- If C: Import mode does NOT require internet. The data is stored inside your Power BI file. You might need internet to refresh it later, but you can work offline.
- If D: Import mode works with ALL source types, including Excel, CSV, and databases. It is the most common connection mode.

---

### Question 2 (Data Sources)

**You need to connect Power BI to three different data sources: a CSV file saved on your desktop, a SQL Server database on your company's network, and a web page with a data table. How many of these can Power BI connect to?**

A) Only 1 — Power BI can only connect to Excel and CSV files  
B) Only 2 — Power BI cannot connect to web pages  
C) All 3 — Power BI can connect to local files, databases, and web sources  
D) None — Power BI needs all data in one file first  

**Correct Answer: C**

**Feedback for incorrect answers:**
- If A: Power BI can connect to many more sources than just Excel/CSV. It connects to databases, cloud services, web pages, and more.
- If B: Power BI CAN connect to web pages. The Web connector is found in Home tab > Get Data > Web.
- If D: One of Power BI's strengths is connecting to MULTIPLE different sources and combining them.

---

### Question 3 (Power Query Profiling)

**You opened the Power Query Editor and turned on Column Quality for a column called "Phone_Number." The Column Quality bar shows: 82% Valid, 3% Error, 15% Empty. What does "15% Empty" tell you?**

A) 15% of the phone numbers are wrong or misspelled  
B) 15% of the rows have no value at all in the Phone_Number column (they are null/blank)  
C) 15% of the phone numbers are duplicates  
D) The Phone_Number column is only 15% complete  

**Correct Answer: B**

**Feedback for incorrect answers:**
- If A: Wrong or misspelled values would show up as "Error" or would appear as "Valid" (Column Quality cannot detect misspellings — it only checks if a value exists and has the right data type). Empty means there is simply no value in that cell.
- If C: Column Quality does not check for duplicates. To see duplicates, use Column Distribution or Column Profile.
- If D: Actually 85% is complete (82% Valid + 3% Error). The 15% empty means 15% of rows have nothing in that cell.

---

### Question 4 (Power Query vs. Main Window)

**A classmate says: "I opened Power BI Desktop and I can see the Power Query Editor." You notice their screen shows the Report View with a blank canvas and the Visualizations pane on the right. Are they actually in the Power Query Editor?**

A) Yes — the Power Query Editor is the main Power BI screen  
B) No — the Power Query Editor is a SEPARATE window. They need to click "Transform Data" on the Home tab to open it.  
C) Yes — the Power Query Editor and Report View are the same thing  
D) No — the Power Query Editor can only be opened from Excel, not Power BI  

**Correct Answer: B**

**Feedback for incorrect answers:**
- If A: The main Power BI Desktop screen (with Report View, Table View, Model View) is NOT the Power Query Editor. The Power Query Editor is a separate window with its own green-themed ribbon.
- If C: Report View and the Power Query Editor are completely different. Report View is for building visuals. Power Query Editor is for cleaning and transforming data.
- If D: The Power Query Editor is built INTO Power BI Desktop. You open it by clicking Transform Data on the Home tab.

---

### Question 5 (Data Profiling — Identifying Issues)

**You are profiling a column called "Event_Date" and you notice that Column Distribution shows 13 distinct values and 13 unique values out of 15 rows. Column Quality shows 87% Valid and 13% Empty. What can you conclude?**

A) There are duplicate dates in the column  
B) 2 rows are missing dates (they are null/blank), and the remaining 13 dates are all different from each other  
C) The column has 13 errors  
D) All 15 dates are present but 2 are formatted incorrectly  

**Correct Answer: B**

**Feedback for incorrect answers:**
- If A: If distinct = unique = 13, there are NO duplicates among the values that exist. Distinct counts how many different values there are. Unique counts values that appear exactly once. When they match, every value is different.
- If C: Column Quality says 87% Valid, not 87% Error. Valid means the values are present and have the correct data type.
- If D: If 2 dates were formatted incorrectly, they might show as Errors (3% Error), not Empty. Empty specifically means no value at all — the cell is blank.

---

## CONFIDENCE CHECK (Ungraded)

**How confident do you feel about the topics covered in Weeks 1-7?**

- Very confident — I understand connecting to data and profiling well
- Somewhat confident — I get the basics but some parts are fuzzy  
- I need to review — I would benefit from going over this material again

*(This question is not graded. It helps your instructor know where the class stands.)*
