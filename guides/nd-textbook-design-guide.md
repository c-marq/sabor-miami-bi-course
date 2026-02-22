# Neurodivergent Textbook Design Guide

**CAP2791C: Power BI Data Preparation and Modeling**  
**Miami Dade College | Business Intelligence Certification**  
**Prepared for the Textbook Creator Project | February 2026**

> **How to use this document:** Feed this guide into your textbook creator project **before** generating any chapter content. Every rule in this document is non-negotiable for the ND student population. The guide covers structure, formatting, language, GUI instruction patterns, DAX-specific rules, assessment design, and a full quality checklist.

---

## 1. Purpose

This document is a companion to the CAP2791C Textbook Table of Contents. It provides the formatting rules, structural patterns, language standards, and UDN (Universal Design for Neurodivergence) requirements that every chapter must follow.

The textbook has **4 Parts, 12 Chapters, and approximately 74 subchapters**. Each chapter follows the same six-part structure. This guide specifies exactly how each part should be written, formatted, and paced for neurodivergent learners.

---

## 2. Chapter Structure (Mandatory Six Parts)

Every chapter follows this exact sequence. Do not skip, reorder, or combine any part.

| Order | Element | Purpose | Target Length |
|-------|---------|---------|---------------|
| 1 | **Why It Matters** | Real-world scenario that frames the chapter. Answers: what problem does this solve? Who uses this in a real job? | 200–300 words (~1 page) |
| 2 | **Concept Breakdown** | Core ideas explained with analogies BEFORE opening Power BI. No screenshots in this section. Build mental models first. | 500–800 words (~2–3 pages) |
| 3 | **Hands-On Walkthrough** | Instructor-led demo with annotated steps. Every click described using the See It, Name It, Find It, Do It pattern. Screenshots referenced for every new interface element. | 800–1200 words + screenshots (~3–5 pages) |
| 4 | **Practice Exercise** | Student-completed lab using the Sabor Miami dataset. Includes Launch Pad, phased steps, checkpoints, and What Success Looks Like screenshot. | 600–1000 words + screenshots (~3–4 pages) |
| 5 | **Checkpoint Quiz** | 5–8 scenario-based questions. No tricks. Immediate feedback. Tests comprehension of THIS chapter only. | 5–8 questions (~1–2 pages) |
| 6 | **Reflection Prompt** | Connect material to student experience or career goals. One open-ended question. Ungraded. | 1 prompt (~3–5 sentences) |

**Total chapter target:** 3,000–4,000 words, designed for 15–20 minute reading time (excluding screenshots and quiz questions).

---

## 3. Chunking Rules

**No content block should require more than 10 minutes of sustained attention without a transition marker or interaction point.**

### 3.1 Named Sections
- Break each chapter part into named subsections of **500–800 words**
- Every subsection gets a clear header visible in the document outline
- Open each subsection with a one-sentence preview: *"In this section, you will learn how to..."*
- Close each subsection with a micro-checkpoint: one question or one "try this" prompt

### 3.2 Progress Indicators
- Every chapter shows **"Chapter X of 12"** in the header or opening line
- Every subsection shows **"Section X.Y of X.Z"** (e.g., "Section 4.3 of 4.5")
- Practice exercises show phase progress: **"Phase 2 of 4: Explore"**

### 3.3 Transition Cues
Between every chunk, include an explicit transition sentence connecting what was just covered to what comes next. These are not optional filler — they are cognitive bridges that reduce the attention cost of task-switching.

> **Example:** "Now that we have seen how Power Query shows us the quality of each column, let us learn what to DO about the problems it reveals. In the next section, we fix our first data issue: null values."

---

## 4. Visual Formatting Standards

### 4.1 Typography
- **Body font:** Segoe UI, 12pt minimum, 14pt preferred for instructional content
- **Headers:** Segoe UI Bold (H1: 16pt, H2: 14pt, H3: 13pt)
- **Code/formulas** (DAX, M code): Consolas or Cascadia Mono, 13pt minimum, with syntax highlighting
- **No italics for emphasis** in body text — use **bold** or color-coded boxes instead
- **All body text left-aligned.** Never center body text (disrupts reading flow for dyslexic readers)

### 4.2 The Five-Box System

Use these five color-coded instructional boxes consistently across every chapter. Students will learn to recognize them visually.

#### ✅ DO THIS (Green)
Action steps — what to click, type, drag, or run. Every step starts with a verb. One action per step.

```html
<div style="background-color: #D5F5E3; border-left: 5px solid #27AE60; padding: 15px; margin: 15px 0; border-radius: 4px;">
  <strong style="color: #1E8449;">✅ DO THIS</strong><br>
  [Action content here]
</div>
```

#### 💡 WHY ARE WE DOING THIS? (Blue)
Context and rationale behind the step or concept. Answers: "Why does this matter?"

```html
<div style="background-color: #D6EAF8; border-left: 5px solid #2E86C1; padding: 15px; margin: 15px 0; border-radius: 4px;">
  <strong style="color: #1A5276;">💡 WHY ARE WE DOING THIS?</strong><br>
  [Rationale content here]
</div>
```

#### ⚠️ COMMON MISTAKE (Yellow)
Warnings about frequent errors and how to avoid or fix them. Include the actual error message if applicable.

```html
<div style="background-color: #FEF9E7; border-left: 5px solid #F1C40F; padding: 15px; margin: 15px 0; border-radius: 4px;">
  <strong style="color: #7D6608;">⚠️ COMMON MISTAKE</strong><br>
  [Warning content here]
</div>
```

#### 🛑 STOP AND CHECK (Red)
Verification checkpoint — confirm output before proceeding. Always include what the student SHOULD see on screen.

```html
<div style="background-color: #FADBD8; border-left: 5px solid #E74C3C; padding: 15px; margin: 15px 0; border-radius: 4px;">
  <strong style="color: #922B21;">🛑 STOP AND CHECK</strong><br>
  [Checkpoint content here]
</div>
```

#### 💜 TAKE A BREATH (Purple)
Cognitive/sensory reset. Use between major transitions, before hard sections, after error-heavy exercises, and at the midpoint of any chapter.

```html
<div style="background-color: #E8DAEF; border-left: 5px solid #8E44AD; padding: 15px; margin: 15px 0; border-radius: 4px;">
  <strong style="color: #6C3483;">💜 TAKE A BREATH</strong><br>
  [Reset/break content here]
</div>
```

**When to use the Purple Box:**
- Between major content transitions
- Before particularly challenging sections
- After error-heavy exercises where frustration may build
- At the midpoint of any chapter

**Example purple box content:**
> 💜 **TAKE A BREATH** — You just profiled your first real dataset. That is a skill people use every day in data jobs. Stretch, look away from your screen, or grab some water. The next section builds on what you just did.

### 4.3 White Space and Layout
- Generous spacing between all elements — never pack content tightly
- One concept per visual region (no multi-panel figures without explicit reading order)
- Horizontal rules or section-complete markers between major sections
- Screenshots always have white space above and below

---

## 5. GUI Instruction Pattern: See It, Name It, Find It, Do It

**Every interaction with Power BI Desktop follows this four-step pattern.** This is the single most important formatting rule in the textbook.

| Step | What It Does | Example |
|------|-------------|---------|
| **1. See It** | Reference an annotated screenshot or visual description | "See Figure 4.1 below: the Column Quality bar appears directly below each column header." |
| **2. Name It** | State the exact name of the button, tab, menu, pane, or field | "This is the **Column Quality** indicator." |
| **3. Find It** | Describe the precise location: which tab, which side of screen, relative position | "It is located in the **View tab** of the Power Query Editor ribbon, in the **Data Preview** section (third group from the left)." |
| **4. Do It** | State the single action: click, drag, type, select, right-click | "Check the box next to **Column Quality** to turn it on." |

### 5.1 Click-Path Notation
For multi-step navigation, use arrow notation. Always include which tab or view to start from.

```
View tab → Data Preview section → Column Quality (check the box)
Home tab → Close & Apply → Close & Apply (the top option)
```

**Never begin a click-path from an ambiguous location.**

### 5.2 "Where Am I?" Anchors
Power BI has four distinct views plus the Power Query Editor. Before every procedural step, confirm which view the student should be in.

> **Example:** "Make sure you are in the **Power Query Editor** (the separate window with the green ribbon, not the main Power BI window). If you do not see the Power Query Editor, go to the **Home tab** in the main Power BI window and click **Transform Data**."

---

## 6. Practice Exercise Format

### 6.1 Launch Pad (Required Before Every Exercise)

Every practice exercise opens with a Launch Pad block:

```
┌─────────────────────────────────────────────┐
│ 🚀 LAUNCH PAD                              │
│                                             │
│ What you are building: [1 sentence]         │
│ Tool: Power BI Desktop → [specific view]    │
│ File to open: [exact filename]              │
│ Data source: [which Sabor Miami file(s)]    │
│ Time estimate: [X–Y minutes]               │
│ Number of steps: [count]                    │
│ What "done" looks like: [1 sentence]        │
│ Start here → [specific first action]        │
└─────────────────────────────────────────────┘
```

### 6.2 Phase Labels
Every exercise is broken into 4 phases, clearly labeled and visually distinct:
1. **Setup** — Open files, confirm view, verify starting state
2. **Explore** — Examine the data/interface before making changes
3. **Build** — Perform the core task (cleaning, transforming, modeling, DAX)
4. **Verify** — Check output against expected results, STOP AND CHECK

### 6.3 Step Rules
- **Maximum 5 top-level steps** per exercise phase
- Each step starts with a **verb:** Click, Select, Type, Drag, Right-click, Navigate, Open, Save
- **One action per step.** Never combine actions.
- Include a **STOP AND CHECK** box after every 1–2 steps with expected screen state
- When referencing information from a previous step, **repeat that information.** Do not assume students will scroll back.

---

## 7. Language and Tone Rules

### 7.1 Banned Words and Phrases

| Never Write | Why | Write Instead |
|-------------|-----|---------------|
| "simple" / "easy" / "just" | Implies failure is student's fault | "This formula has three parts. Let us take them one at a time." |
| "obviously" / "of course" | Assumes shared knowledge | State the fact directly without qualifier |
| "you should already know this" | Triggers shame for students who may not recall | "Let us refresh this concept before we build on it." |
| "as we discussed earlier" | ND students may not remember | Repeat the relevant information or link to the section |
| "simply click..." | Minimizes steps that may not feel simple | Use the See It, Name It, Find It, Do It pattern |

### 7.2 Normalizing Difficulty
Before every hard section, include a sentence that explicitly normalizes struggle:

> "This next concept is where most students need to read it twice. That is completely normal. Read through it once to get the general idea, then come back and follow the steps."

> "Filter context is the single most confusing concept in DAX. Professional Power BI developers struggled with this when they first learned it. Give yourself permission to be confused right now."

### 7.3 Error Framing
Errors are detective work, not failure:
- "The error is telling us something. Let us read it like a clue."
- "This error means Power BI expected a number but found text. Where might text be hiding in our data?"
- Never frame unexpected results as mistakes: "Your total is different from the expected output. That tells us something about our data. Let us investigate."

### 7.4 Consistent Verb-Object Pairs

| Action | Always Use | Never Use |
|--------|-----------|-----------|
| Mouse left-click | **Click** | Press, hit, tap, select (when clicking) |
| Mouse right-click | **Right-click** | Secondary click, context click |
| Choose from dropdown | **Select** | Pick, choose, click (for dropdowns) |
| Enter text | **Type** | Enter, input, write, key in |
| Move element to area | **Drag** | Move, pull, place |

---

## 8. Vocabulary Handling

**Every technical term must be defined inline on its first use in each chapter.** Even if the term was defined in a previous chapter, define it again. ND learners may not retain definitions across sessions.

### 8.1 Definition Format
On first use in a chapter, bold the term and provide a parenthetical definition:

> "Open the **Power Query Editor** (the separate workspace inside Power BI where you clean and transform data before it enters your model). You can find it by clicking **Transform Data** on the Home tab."

### 8.2 Running Glossary
- Each **chapter** ends with a mini-glossary of terms introduced or reintroduced
- Each **Part** ends with a cumulative Part glossary
- The **textbook** has a master glossary at the end
- All three levels are required

### 8.3 Cross-Tool Vocabulary Bridges

Since students have completed Intro to Data Analytics (Excel) and Intro to Database Design (MySQL/SQL), connect new Power BI terms to what they already know:

| Power BI Term | Excel Equivalent | SQL Equivalent | Bridge Sentence |
|--------------|-----------------|----------------|-----------------|
| Query (Power Query) | Worksheet / Table | SELECT statement | "A query in Power Query is like a worksheet in Excel or a SELECT statement in SQL." |
| Merge Queries | VLOOKUP | JOIN | "Merging is the Power BI version of JOIN in SQL." |
| Append Queries | Copy-paste rows below | UNION | "Appending stacks tables vertically, like UNION in SQL." |
| Relationship | VLOOKUP link | FOREIGN KEY | "A relationship connects two tables, like a foreign key in your database." |
| Measure (DAX) | Formula in a cell | Aggregate function | "A measure is like a formula, but it calculates on the fly." |
| Filter Context | Filter dropdown | WHERE clause | "Filter context is like a WHERE clause that is always running." |
| Applied Steps | Undo history | — | "Each step is a recorded action. You can go back to any point." |
| Close & Apply | Save + close | — | "This saves your Power Query work and loads it into the model." |

---

## 9. Screenshot Standards

- **One highlight per screenshot.** Do not annotate five things in one image.
- Use **numbered red circles or red boxes** to highlight the target area.
- Every screenshot has a caption: **"Figure X.Y: [What this shows]"**
- Multi-click sequences use **multiple screenshots** (one per click), not one screenshot with multiple annotations.
- **Alt text required** on all screenshots for accessibility.
- Screenshots must show the **full relevant portion** of the interface, not a tiny crop that loses context.
- When Power Query and the main Power BI window could be confused, **always indicate which window** the screenshot is from.

---

## 10. DAX-Specific Instruction Rules

These rules apply to Chapters 11 and 12 and any earlier chapter that previews DAX measures.

### 10.1 English First, DAX Second
Every new DAX expression is introduced with a plain-English question first:

> **What we want to ask:** "What is the total of all sales amounts?"
>
> **In DAX:**
> ```dax
> Total Sales = SUM(Sales[Amount])
> ```
>
> **What this does:** The SUM function adds up every value in the Amount column of the Sales table.

### 10.2 Query Anatomy Callouts
For any DAX expression with more than one function or argument:

```dax
YTD Sales =
  TOTALYTD(              ← calculate a year-to-date running total
    SUM(Sales[Amount]),   ← what to total (sales amounts)
    'Date'[Date]          ← which date column to use for YTD logic
  )
```

### 10.3 DAX Keyword Translations

| DAX Function | Plain English | Introduced In |
|-------------|--------------|---------------|
| SUM | Add up all the values in a column | Chapter 11 |
| AVERAGE | Find the average value across a column | Chapter 11 |
| COUNT / COUNTROWS | Count how many items or rows there are | Chapter 11 |
| DISTINCTCOUNT | Count unique values only (no duplicates) | Chapter 11 |
| DIVIDE | Divide safely (no error if dividing by zero) | Chapter 11 |
| CALCULATE | Recalculate something with different filters applied | Chapter 11 |
| TOTALYTD | Running total from January 1 to the current date | Chapter 12 |
| SAMEPERIODLASTYEAR | Look at the same dates but one year earlier | Chapter 12 |
| DATEADD | Shift dates forward or backward by a specified interval | Chapter 12 |

### 10.4 DAX Error Handling
For every DAX exercise, include a "Common Errors" section:
- Show the **actual error message** text the student will see
- Provide a **plain-English translation** of what it means
- Give a **specific fix** (not just "check your formula")

---

## 11. Power BI View Compass

Include this reference at the beginning of every chapter and exercise that changes views.

| View | What You See | What You Do Here | Chapters |
|------|-------------|-------------------|----------|
| **Report View** | Canvas with visuals (charts, tables, cards) | Build reports, verify DAX measures visually | 11, 12 |
| **Table View** | Data rows in a spreadsheet-like grid | Inspect data values, check calculated columns | 8, 10, 11 |
| **Model View** | Table boxes with lines showing relationships | Create and manage relationships between tables | 8, 9, 10 |
| **DAX Query View** | Code editor for testing DAX | Test and debug DAX measures | 11, 12 |
| **Power Query Editor** | SEPARATE WINDOW with green ribbon, steps pane, data preview | Clean, transform, and load data BEFORE it enters the model | 4, 5, 6, 7 |

**Critical reminder:** The Power Query Editor is a **separate window**. Every transition between the main Power BI window and Power Query needs a WHERE AM I? anchor.

---

## 12. Course Dataset: Sabor Miami

All Practice Exercises and Hands-On Walkthroughs use the **Sabor Miami** dataset — a fictional family-owned food truck company operating 4 trucks across Miami-Dade County, serving Latin-Caribbean fusion food at events, lunch spots, and festivals throughout 2024.

### 12.1 Dataset Files

| File | Type | Model Role | Key Fields |
|------|------|-----------|------------|
| SaborMiami_Sales_2024.csv | CSV | Fact Table | Transaction_ID, Date, Truck_ID, Employee_ID, Menu_Item_ID, Amount, Tip |
| SaborMiami_MenuItems.xlsx | Excel | Dimension | Menu_Item_ID, Item_Name, Category, Price |
| SaborMiami_Trucks.xlsx | Excel | Dimension | Truck_ID, Truck_Name, Home_Location, Status |
| SaborMiami_Employees.xlsx | Excel | Dimension | Employee_ID, First_Name, Last_Name, Role, Truck_ID |
| SaborMiami_Events_2024.csv | CSV | Dimension | Event_ID, Event_Name, Event_Type, Event_Date |

A **Date dimension table** will be created by students in Chapter 9. This is a teaching moment — students build it themselves.

### 12.2 Built-In Data Quality Issues
The dataset is intentionally seeded with realistic data quality issues that map to specific chapters and competencies. The Instructor Data Dictionary catalogs every issue. **Do not reveal the complete issue list to students** — they discover issues through profiling in Chapter 4 and fix them in Chapters 5–7.

---

## 13. Assessment Design Within Chapters

### 13.1 Checkpoint Quiz Rules
- **5–8 questions** per quiz, covering ONLY the current chapter
- Question types: screenshot-based identification, output prediction, matching (term → definition), fill-in-the-blank for DAX/M code, short scenario questions
- **No trick questions.** No "all of the above." No "which is NOT."
- Provide a **brief explanation** with every answer (not just correct/incorrect)
- Include a **confidence check** at the end: "How confident do you feel? (Very / Somewhat / Need to review)"

### 13.2 Reflection Prompt Rules
- One open-ended question connecting the chapter to student experience or career goals
- Example: *"Think of a dataset you encounter in your daily life (a bank statement, a playlist, a grade book). What data quality issues might it have?"*
- Ungraded. Purpose is metacognition, not assessment.

---

## 14. Chapter Quality Checklist

Run this checklist against every chapter before finalizing. **Every item must pass.**

### Structural Checks
- [ ] All six chapter parts present in correct order
- [ ] Chapter number and progress indicator in opening
- [ ] Subsections labeled with X.Y numbering
- [ ] No content block exceeds 10 minutes without a transition
- [ ] TAKE A BREATH box appears at least once per chapter
- [ ] Transition cues connect every subsection to the next

### Visual Checks
- [ ] All text left-aligned, sans-serif, 12pt minimum
- [ ] Five-box system used correctly (right color for right purpose)
- [ ] Screenshots referenced for every new interface element
- [ ] One highlight per screenshot
- [ ] Alt text on all images
- [ ] View Compass included where view changes occur

### Language Checks
- [ ] No banned words (simple, easy, obvious, just, simply)
- [ ] No assumed knowledge without definition or refresher
- [ ] Consistent verb-object pairs throughout
- [ ] Every technical term defined on first use in this chapter
- [ ] Difficulty normalized before hard sections
- [ ] Errors framed as investigation, not failure

### Exercise Checks
- [ ] Launch Pad block present
- [ ] Phases labeled (Setup → Explore → Build → Verify)
- [ ] Maximum 5 top-level steps per phase
- [ ] One action per step
- [ ] STOP AND CHECK after every 1–2 steps
- [ ] What Success Looks Like section with expected output
- [ ] Time estimate included
- [ ] Sabor Miami dataset used consistently

### DAX-Specific Checks (Chapters 11–12)
- [ ] English First, DAX Second pattern used for all new expressions
- [ ] Query Anatomy callout for complex expressions
- [ ] Every DAX function has a plain-English translation
- [ ] Common error messages explained
- [ ] Filter context explicitly called out where relevant

---

> **Feed this document into your textbook creator project before generating any chapter. The rules in this guide are non-negotiable for the ND student population.**
