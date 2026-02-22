# SEMESTER TRIAGE PLAN — Weeks 8–16

**CAP2791C: Power BI Data Preparation and Modeling | ND Section**  
**2 Sessions per Week | 100 Minutes per Session**  
**Format: Session A = Teach + Guided Practice | Session B = Lab + Assessment**

---

## Week-by-Week Overview

| Wk | Session A (Teach) | Session B (Lab) | Assessment | Competencies |
|----|-------------------|-----------------|------------|--------------|
| 8 | Reset, Regroup, Roadmap + Intro Sabor Miami Dataset | Data Quality Snapshot Lab (ungraded) + Comp Check #1 | Comp Check #1 (10 pts) | C1–C2 Review |
| 9 | Cleaning: Nulls, Inconsistencies, Naming, Data Types | Graded Lab #1: Data Cleaning | Lab #1 (50 pts) | C3.1, C3.2, C3.7 |
| 10 | Transforms: Text, Numerical, Grouping, Pivot/Unpivot | Transform Practice + Comp Check #2 | Comp Check #2 (10 pts) | C3.4, C3.5 |
| 11 | Combining Queries: Merge, Append, Keys + M Code Preview | Graded Lab #2: Combined Dataset | Lab #2 (50 pts) | C3.3, C3.6, C3.8 |
| 12 | Data Modeling: Tables, Relationships, Star Schema | Modeling Practice + Comp Check #3 + Portfolio Checkpoint | Comp Check #3 (10 pts) | C4.1, C4.5, C4.8, C5.1 |
| 13 | DAX Fundamentals: SUM, COUNT, AVG, DISTINCTCOUNT, DIVIDE | Graded Lab #3: Measure Library | Lab #3 (50 pts) | C6.1, C6.2, C6.5 |
| 14 | CALCULATE + Filter Context + Time Intelligence | Advanced DAX Practice + Comp Check #4 | Comp Check #4 (10 pts) | C6.3, C6.4, C6.6 |
| 15 | Optimization Overview + Portfolio Assembly Workshop | Graded Lab #4: Polished Model + Portfolio Work | Lab #4 (50 pts) | C4.2–C4.9, C5.2–C5.4, C7 |
| 16 | Final Project Work: Independent Dataset | Share-Out (Optional) + Course Wrap-Up | Portfolio (150 pts) | All (C1–C7) |

---

## Revised Assessment Structure (Weeks 8–16)

| Assessment | Points | When | Format | Policy |
|------------|--------|------|--------|--------|
| Comprehension Checks (4) | 40 | Wk 8, 10, 12, 14 | 5–8 questions, untimed, retakable (3 attempts), immediate feedback | Highest score kept |
| Applied Labs (4) | 200 | Wk 9, 11, 13, 15 | Structured Power BI tasks with starter files, checkpoints, rubric | 48-hr grace, redo available, 10%/day cap 30% |
| Portfolio Project | 150 | Wk 16 | Assembled .pbix from all labs + independent dataset + reflection/walkthrough | Midterm checkpoint in Wk 12 (ungraded feedback) |
| Participation | 50 | Ongoing | Attendance + engagement | Same as current |
| **TOTAL (Weeks 8–16)** | **440** | | | |

**Final course grade** = (Weeks 1–7 earned points) + (Weeks 8–16 earned points out of 440). Communicate each student's current standing explicitly in Week 8.

---

## Detailed Session Plans

---

### WEEK 8: Reset, Regroup, and Relaunch

**Purpose:** Psychological and structural reset. Students start the second half with a clear map, new policies, and the Sabor Miami dataset.

#### Session 8A (TOMORROW): The New Map + Sabor Miami Introduction

**Focus:** Reset, communicate new structure, connect to dataset

| Segment | Time | Activity | UDN Note |
|---------|------|----------|----------|
| Arrival & Grounding | 5 min | Slide: "Welcome to the Second Half." Agenda visible on screen. Calm, forward-looking tone. | Reduces ambiguity anxiety |
| The New Map | 10 min | Show the 8-week roadmap visual. Walk through what students build each week. "Everything you have done so far counts." | Executive Function scaffold |
| New Policies | 5 min | Announce revised late policy (48-hr grace), redo policy, no timed quizzes. Let it land. Answer questions. | Emotional Regulation |
| Intro Sabor Miami | 8 min | Introduce the fictional business. Show the 5 data files. "This is YOUR data for the rest of the semester." | Engagement anchor |
| Hands-On: Connect | 15 min | Students connect to the Sabor Miami CSV and Excel files in Power BI. Review of Weeks 1–3 skills applied to new data. | Confidence builder |
| 💜 TAKE A BREATH | 3 min | "You just connected to the data you will work with for the rest of the course." | Sensory reset |
| Guided Profiling | 20 min | Walk through Column Quality, Distribution, Profile on the Sales table. Students follow along. Point out issues: mixed dates, nulls, duplicates. | Review + new data |
| Wrap-Up | 5 min | "Next class: you will document the problems you found." Save reminder. | Closure |

#### Session 8B: Data Quality Snapshot + Comprehension Check #1

**Focus:** Document data issues, low-stakes assessment on Weeks 1–7

| Segment | Time | Activity | UDN Note |
|---------|------|----------|----------|
| Arrival & Grounding | 5 min | "Today you become data detectives. Your job is to find every problem hiding in the Sabor Miami data." | Framing as investigation |
| Review | 5 min | Quick recap of profiling tools from 8A. Show which tables to examine. | Working memory support |
| Lab: Quality Snapshot | 35 min | Students profile all 5 tables and document issues on the provided template. Target: at least 10 issues. Ungraded. | Executive Function: template reduces ambiguity |
| 💜 TAKE A BREATH | 3 min | "You have just done what real data analysts do in the first hour of any project." | Validation |
| Gallery Walk (optional) | 10 min | Students who want to share their findings can show their screen. Others listen. Completely optional. | Social: opt-in only |
| Comp Check #1 | 15 min | 5 questions covering Weeks 1–7. In Canvas, untimed, 3 attempts. | Low-stakes retrieval practice |
| Wrap-Up | 5 min | "Next week we START FIXING. Everything you found today gets cleaned." Save reminder. | Forward momentum |

---

### WEEK 9: Cleaning Your Data

**Competencies:** C3.1, C3.2, C3.7 — Students produce their first clean dataset.

#### Session 9A: Cleaning Techniques Demo

**Focus:** Nulls, inconsistencies, naming, data types in Power Query

| Segment | Time | Activity | UDN Note |
|---------|------|----------|----------|
| Arrival & Grounding | 5 min | "Last class you found the problems. Today you fix them." Show before/after comparison. | Concrete goal |
| Review | 5 min | Pull up the Data Quality Snapshot from 8B. "Here are the issues we found." | Connect to prior work |
| Teach: Nulls | 12 min | Live demo: Remove Rows with errors, Replace Values, Fill Down. Use Sales table (null tips). | See It Name It Find It Do It |
| 💜 TAKE A BREATH | 2 min | | |
| Teach: Inconsistencies | 12 min | Live demo: Trim, Clean, Proper case, Replace Values for category standardization (Menu Items). Rename columns. | Multiple representations |
| Teach: Data Types | 8 min | Change Price column from text to currency (remove $). Fix date column type. Show error handling. | Common error preview |
| Guided Practice | 20 min | Students replicate all demos on their own files step by step. Companion Guide available for struggling students. | Bridge demo → independent |
| Wrap-Up | 5 min | "Save your file. Next class you clean the full dataset for your first graded lab." | |

#### Session 9B: Graded Lab #1 — Data Cleaning

**Focus:** Independent cleaning of full Sabor Miami dataset

| Segment | Time | Activity | UDN Note |
|---------|------|----------|----------|
| Arrival & Grounding | 5 min | "Today is your first graded lab. You have the tools. Use your notes." | Reduce anxiety |
| Quick Review | 5 min | 3-slide review of cleaning techniques. Show the rubric. | Clarity on expectations |
| Lab #1 Work Time | 55 min | Students clean the full dataset. Starter file provided. Checkpoints at 15 and 35 min. What Success Looks Like screenshot visible on projector. | Generous time + checkpoints |
| 💜 TAKE A BREATH | 3 min | At the 40-minute mark: "If you are not done, that is fine. Focus on the most important fixes." | Normalize pace differences |
| Final Save + Submit | 5 min | Walk through submission process in Canvas. | Prevent tech anxiety |
| Preview Week 10 | 5 min | "Your data is clean. Next week we reshape it: split columns, group data, pivot tables." | Forward momentum |

---

### WEEK 10: Transforming and Reshaping Data

**Competencies:** C3.4, C3.5 — Text transforms, numerical operations, grouping, pivoting.

#### Session 10A: Transformation Techniques Demo

**Focus:** Split, merge, trim, group, pivot, unpivot in Power Query

| Segment | Time | Activity | UDN Note |
|---------|------|----------|----------|
| Arrival & Grounding | 5 min | "Your data is clean. Now we reshape it to answer business questions." | Connect to prior week |
| Review | 5 min | Open cleaned file from Lab #1. Quick check: does everyone's data look right? | Catch stragglers |
| Teach: Text Transforms | 12 min | Split Column (by delimiter), Merge Columns, Extract. Use Employee names as example. | Concrete operations |
| 💜 TAKE A BREATH | 2 min | | |
| Teach: Grouping + Pivoting | 15 min | Group By (total sales per truck). Pivot vs Unpivot with before/after. WHY box for each. | Abstract concept grounding |
| Guided Practice | 25 min | Students apply 4–5 specific transforms to Sabor Miami data following step-by-step instructions. | Bridge |
| Wrap-Up | 5 min | "Save. Next class: comprehension check and more practice." | |

#### Session 10B: Transform Practice + Comprehension Check #2

**Focus:** Reinforcement and low-stakes assessment

| Segment | Time | Activity | UDN Note |
|---------|------|----------|----------|
| Arrival & Grounding | 5 min | "Today: practice what you learned, then a quick check." | Clear agenda |
| Extended Practice | 40 min | Practice worksheet with 6 transformation tasks. Ungraded but exact skills needed for Lab #2 next week. | Rehearsal for graded work |
| 💜 TAKE A BREATH | 3 min | "Transformations are about changing data shape. You are reshaping, not breaking." | Normalize confusion |
| Comp Check #2 | 15 min | 6 questions on cleaning + transformation. Canvas, untimed, 3 attempts. | Retrieval practice |
| Preview Week 11 | 5 min | "Next week: merging tables together. Just like JOINs in SQL." | Bridge to prior knowledge |

---

### WEEK 11: Combining Queries

**Competencies:** C3.3, C3.6, C3.8 — Merge, append, keys, M code intro.

#### Session 11A: Merge and Append Queries Demo

**Focus:** Join types, appending, reference/duplicate, keys

| Segment | Time | Activity | UDN Note |
|---------|------|----------|----------|
| Arrival & Grounding | 5 min | "Remember JOINs in SQL? Today we do the same thing in Power BI — visually." | Cross-tool bridge |
| Teach: Merge Queries | 15 min | Left Join demo with Sales + Menu Items. Show SQL equivalent side by side. Name each join type, show when to use. | Dual representation |
| 💜 TAKE A BREATH | 2 min | | |
| Teach: Append + Keys | 10 min | Append two files. Creating keys for joins. Reference vs Duplicate query. | |
| Teach: M Code Preview | 8 min | Open Advanced Editor. Read 3 lines of M, translate to English. "You do not write this; you read it." | Reduce intimidation |
| Guided Practice | 25 min | Students merge Sales with Menu Items and Trucks. Check relationships in the Queries pane. | Bridge |
| Wrap-Up | 5 min | "Next class: graded lab. You will combine ALL tables." | |

#### Session 11B: Graded Lab #2 — Combined & Loaded Dataset

**Focus:** Merge all tables, configure loading

| Segment | Time | Activity | UDN Note |
|---------|------|----------|----------|
| Arrival & Grounding | 5 min | Show rubric. Show What Success Looks Like screenshot. | Clear expectations |
| Quick Review | 5 min | 3-slide review of merge types and when to use each. | |
| Lab #2 Work Time | 55 min | Students produce a .pbix with all queries merged, keyed, and loaded. Checkpoints at 15 and 35 min. | Generous time |
| 💜 TAKE A BREATH | 3 min | | |
| Save + Submit | 5 min | Walk through submission. | |
| Preview | 5 min | "Your data is clean, transformed, and combined. Next week: we build the MODEL." | |

---

### WEEK 12: Data Modeling

**Competencies:** C4.1, C4.5, C4.8, C5.1 — Tables, relationships, star schema, date table.

#### Session 12A: Data Modeling Fundamentals

**Focus:** Model View, fact vs dimension, relationships, cardinality

| Segment | Time | Activity | UDN Note |
|---------|------|----------|----------|
| Arrival & Grounding | 5 min | "You have been preparing ingredients. Today you design the kitchen." Show star schema diagram. | Visual goal |
| Teach: What Is a Model? | 10 min | Model View orientation (WHERE AM I? anchor — new view). Fact = Sales. Dimensions = everything else. | New view introduction |
| 💜 TAKE A BREATH | 3 min | "This is the most conceptual day. Normal if it feels abstract." | Pre-normalize difficulty |
| Teach: Relationships | 12 min | Drag to create relationships. One-to-many. Cross-filter. Use Sabor Miami tables. | Concrete examples |
| Teach: Date Table | 10 min | Create date table with CALENDARAUTO() or provided M template. "This powers time intelligence in Week 14." | Forward connection |
| Guided Practice | 25 min | Students build their star schema: 4–5 relationships + date table. Checkpoint screenshot. | |
| Wrap-Up | 5 min | "You have a data model. Next class: verify it and check understanding." | |

#### Session 12B: Modeling Practice + Comp Check #3 + Portfolio Checkpoint

**Focus:** Verify model, assessment, mid-semester check-in

| Segment | Time | Activity | UDN Note |
|---------|------|----------|----------|
| Arrival & Grounding | 5 min | "Today: verify your model is correct, then a quick check." | |
| Model Verification | 20 min | Verify star schema using provided checklist. Fix relationship issues. Create simple table visual to confirm data flows. | Catch errors before DAX |
| Comp Check #3 | 15 min | 6 questions: fact vs dimension, cardinality, relationship types. | |
| 💜 TAKE A BREATH | 3 min | | |
| Portfolio Check-In | 20 min | Show portfolio template. Students assess progress: which pieces done, which need work. Ungraded peer review available. | Executive Function: progress visibility |
| Preview | 5 min | "Next week: DAX. You will make your model come alive with calculations." | Build anticipation |

---

### WEEK 13: DAX Fundamentals

**Competencies:** C6.1, C6.2, C6.5 — SUM, COUNT, AVERAGE, DISTINCTCOUNT, DIVIDE, measures vs columns.

#### Session 13A: Your First DAX Measures

**Focus:** Write 5+ measures, display in visuals

| Segment | Time | Activity | UDN Note |
|---------|------|----------|----------|
| Arrival & Grounding | 5 min | "Power Query shaped data BEFORE the model. DAX creates calculations INSIDE the model." Pipeline diagram. | Position in workflow |
| Teach: SUM, COUNT, AVG | 12 min | English First, DAX Second pattern. Write `Total Sales = SUM(Sales[Amount])`. Show in Card visual IMMEDIATELY. | Visible result quickly |
| 💜 TAKE A BREATH | 3 min | "You just wrote your first DAX measure. That is a real professional skill." | Celebrate milestone |
| Teach: DISTINCTCOUNT, DIVIDE | 10 min | Unique customers, safe division. Measure vs calculated column explanation. | |
| Guided Practice | 25 min | Students write 6 measures following exact examples. Each displayed in a visual. | Replication before independence |
| Preview | 5 min | "Next class: graded lab — you will build a full measure library." | |

#### Session 13B: Graded Lab #3 — Measure Library

**Focus:** 8 specified measures in visuals

| Segment | Time | Activity | UDN Note |
|---------|------|----------|----------|
| Arrival & Grounding | 5 min | Show rubric, What Success Looks Like screenshot. | |
| Quick Review | 5 min | DAX syntax review. Remind: English First, then DAX. | |
| Lab #3 Work Time | 55 min | Students create 8 measures and place in visuals. Starter: modeled .pbix. Checkpoints at 15 and 35 min. | |
| 💜 TAKE A BREATH | 3 min | | |
| Save + Submit | 5 min | | |
| Preview | 5 min | "Next week: CALCULATE — the most powerful DAX function — and time intelligence." | |

---

### WEEK 14: CALCULATE and Time Intelligence

**Competencies:** C6.3, C6.4, C6.6 — Filter context, CALCULATE, YTD, prior year. **HARDEST WEEK.**

#### Session 14A: CALCULATE and Filter Context

**Focus:** The hardest concept in DAX

| Segment | Time | Activity | UDN Note |
|---------|------|----------|----------|
| Arrival & Grounding | 5 min | "Today is the hardest content day. I am telling you upfront so you know it is normal to struggle." | Pre-normalize difficulty |
| Teach: Filter Context | 15 min | Room metaphor: filters are doors. CALCULATE opens/closes specific doors. Live demo with concrete examples. | Extended teach time for hard content |
| 💜 TAKE A BREATH | 3 min | "Filter context is what professionals struggle with most. Fuzzy is expected right now." | |
| Teach: Time Intelligence | 12 min | TOTALYTD and SAMEPERIODLASTYEAR. Show in line chart. Connect to date table from Week 12. | Visual verification |
| Guided Practice | 25 min | Students write 3 CALCULATE measures and 2 time intelligence measures step by step. | More guided practice for hard content |
| Wrap-Up | 5 min | "This will click more with practice. Next class: practice and comprehension check." | |

#### Session 14B: Advanced DAX Practice + Comp Check #4

**Focus:** Reinforcement of CALCULATE and time intelligence

| Segment | Time | Activity | UDN Note |
|---------|------|----------|----------|
| Arrival & Grounding | 5 min | "Today is practice and consolidation. No new concepts." | Reduce cognitive load expectation |
| Practice Workshop | 35 min | Students experiment with additional CALCULATE filters and time functions. Troubleshooting guide provided. Instructor circulates heavily. | Extended practice |
| 💜 TAKE A BREATH | 3 min | | |
| Comp Check #4 | 15 min | 6 questions on CALCULATE, filter context, time intelligence. | |
| Portfolio Status | 10 min | Quick self-assessment: what is done, what needs work? | Executive Function |
| Preview | 5 min | "Next week: polish everything and assemble your portfolio." | |

---

### WEEK 15: Optimization + Portfolio Assembly

**Competencies:** C4.2–C4.9, C5.2–C5.4, C7 (awareness) — Finishing work.

#### Session 15A: Optimization Essentials + Security Overview

**Focus:** Performance Analyzer, RLS concept, removing clutter

| Segment | Time | Activity | UDN Note |
|---------|------|----------|----------|
| Arrival & Grounding | 5 min | "Two classes left. Today: make your model fast and secure. Then: assemble." | |
| Teach: Optimization | 12 min | Performance Analyzer demo. Remove unnecessary columns. Cardinality concepts. Awareness level. | Conceptual, not deep practice |
| Teach: Security | 8 min | RLS concept and quick demo. Sensitivity labels mentioned. | Awareness level |
| 💜 TAKE A BREATH | 3 min | | |
| Portfolio Workshop | 35 min | Students open most complete .pbix and work from the Portfolio Checklist. Instructor circulates. | Assembly, not creation |
| Wrap-Up | 5 min | "Next class: finish polished model (Lab #4) and keep working on portfolio." | |

#### Session 15B: Graded Lab #4 + Portfolio Finalization

**Focus:** Submit polished model, continue portfolio

| Segment | Time | Activity | UDN Note |
|---------|------|----------|----------|
| Arrival & Grounding | 5 min | Show Lab #4 rubric and portfolio rubric side by side. | |
| Lab #4 + Portfolio Work | 60 min | Combined work session. Lab #4 = polished model. Portfolio adds independent dataset component. | Generous time |
| 💜 TAKE A BREATH | 3 min | | |
| Save + Submit Lab #4 | 5 min | | |
| Preview Week 16 | 5 min | "Final week. Portfolio due. Optional share-out for anyone who wants to present." | |

---

### WEEK 16: Final Project + Course Wrap-Up

**Portfolio submission. Independent dataset component. Celebration.**

#### Session 16A: Final Project Work Time

**Focus:** Independent dataset + portfolio completion

| Segment | Time | Activity | UDN Note |
|---------|------|----------|----------|
| Arrival & Grounding | 5 min | "This is your last working session. Let us finish strong." | |
| Work Time | 55 min | Students finalize portfolio and independent dataset. Instructor provides individual feedback. | Individual attention |
| 💜 TAKE A BREATH | 3 min | | |
| Submission Walkthrough | 10 min | Step-by-step Canvas submission guide. Confirm every student knows how to submit. | Prevent tech issues |
| Preview | 5 min | "Next class is our last. Optional share-out and course wrap-up." | |

#### Session 16B: Share-Out + Course Wrap-Up

**Focus:** Celebrate, reflect, connect to Course 5

| Segment | Time | Activity | UDN Note |
|---------|------|----------|----------|
| Arrival & Grounding | 5 min | "This is the last class of this course. Let us look at what you built." | |
| Share-Out | 25 min | Optional presentations (2–3 min each). Template provided. Written summary acceptable. | Opt-in, no penalty |
| 💜 TAKE A BREATH | 3 min | | |
| Course Reflection | 10 min | "What was the hardest part? What surprised you? What are you most proud of?" Written or verbal. | Metacognition |
| Pipeline Connection | 10 min | Show the 5-course certification map. "In Course 5, you will build dashboards ON TOP of models like this one." | Forward motivation |
| Celebration + Close | 10 min | Acknowledge growth. Thank students. Remind: portfolio due Sunday if not already submitted. | Positive closure |

---

## Policies to Announce in Week 8

### Revised Late Work Policy
- **48-hour grace period:** No penalty for any submission up to 48 hours past the deadline.
- **After 48 hours:** 10% per calendar day.
- **Maximum reduction:** 30%. A late submission always earns more than a zero.
- **Redo and Resubmit:** Students scoring below "Good" on any graded lab may revise and resubmit once for up to the "Good" tier score.

### Revised Quiz Policy
- All comprehension checks are **untimed** and **retakable** (3 attempts, highest score kept).
- **Immediate feedback** on incorrect answers with explanation.

### Portfolio Policy
- Portfolio template distributed in **Week 12B**.
- Portfolio assembles work from Labs 1–4 plus an independent dataset component.
- **Submission options:** .pbix file + written reflection OR .pbix file + recorded screen walkthrough (2–3 min).
- **Presentation is optional.** No penalty for choosing the non-presentation option.

---

## Competency Coverage Summary

| Competency | Coverage Level | Notes |
|------------|---------------|-------|
| C1: Get Data | ✅ Full (Weeks 1–5) | Already completed |
| C2: Profile Data | ✅ Full (Weeks 6–7) | Already completed |
| C3: Clean, Transform, Load | ✅ Full (Weeks 9–11) | Core focus of second half |
| C4: Design a Data Model | ✅ Full (Weeks 12, 15) | Star schema, relationships, date table |
| C5: Develop and Refine | 🟡 Partial | Hierarchies/calc tables = awareness. RLS demoed. Q&A mentioned only. |
| C6: Use DAX | 🟡 Substantial | Basic measures, CALCULATE, time intelligence. Semi-additive/calc groups = awareness. |
| C7: Optimize Performance | 🟡 Awareness | Performance Analyzer demoed. Principles taught conceptually. |
