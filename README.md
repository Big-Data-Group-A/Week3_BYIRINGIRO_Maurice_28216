# Week3_BYIRINGIRO_Maurice_28216
Submission of Week 3 Assignment
# Week 3 Lab — Control Flow & Functions
**AUCA · Introduction to Big Data Analytics**

**Student:** BYIRINGIRO Maurice  
**Student ID:** 28216 
**Instructor:** Prince Ishimwe 

## Lab Overview

This lab covers the core concepts of **Control Flow** and **Functions** in Python:

- Decision making with 'if / elif / else'
- Loops (`for` and `while`) and the accumulator pattern
- Writing reusable functions
- Reading CSV files
- Building a **resilient data pipeline** that survives broken/missing data using `try/except`


  ## Dataset

- File: `week3_students.csv`
- Contains 40 student records
- **3 records have broken scores** (non-numeric values)

### Broken Records Identified

| Student ID   | Problem          |
|--------------|------------------|
| AUCA008      | score = N/A      |
| AUCA020      | score is empty   |
| AUCA032      | score = absent   |

These were successfully detected and skipped using `try/except ValueError`.


## How to Run

1. Make sure `week3_students.csv` is in the same folder as the notebook.
2. Open the notebook: `Week3_BYIRINGIRO_Maurice.ipynb`
3. Run all cells from top to bottom (or use **Run All**).

No external libraries are required — pure Python only.

## Key Results

- **Valid records:** 37  
- **Broken records:** 3  
- **Average of valid scores:** 
- **Top student:** 

  


  
