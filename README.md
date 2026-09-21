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

# Week 3 Lab — Control Flow & Functions

## Introduction to Big Data Analytics

**Institution:** Adventist University of Central Africa (AUCA)
**Instructor:** Prince Ishimwe
**Student Name:** BYIRINGIRO Maurice
**Student ID:** 28216
**Program:** __________________________
**Lab:** Week 3 — Control Flow & Functions
**Total Marks:** 35 + 3 Bonus Marks

---

## 📌 Overview

This repository contains my solution for the **Week 3 Lab — Control Flow & Functions** for the Introduction to Big Data Analytics course.

The lab focuses on fundamental Python programming concepts used in data processing, including:

* Decision making using `if`, `elif`, and `else`
* `for` and `while` loops
* Accumulator patterns
* Python functions
* Reading CSV files
* Exception handling with `try` and `except`
* Processing data containing invalid records
* Dictionary-based aggregation
* Generating a simple text report

The main dataset used in this lab is `week3_students.csv`, which contains student information and includes three records with invalid score values. The purpose of the resilient pipeline is to process the valid records while identifying and surviving the broken records.

---

## 📁 Repository Structure

```text
Week3-Lab/
│
├── Week3_BYIRINGIRO_Maurice.ipynb
├── week3_students.csv
├── README.md
│
└── screenshots/
    ├── pic1.png
    ├── ppic2.png
    ├── pic3.png
    ├── pic4.png
    ├── pic5.png

   
```

---

# Part 1 — Making Decisions

## Exercise 1.1 — The Grading Ladder

The grading system uses an `if / elif / else` ladder to convert a numerical score into a letter grade.

| Score | Grade |
| ----: | :---: |
|  ≥ 85 |   A   |
| 70–84 |   B   |
| 60–69 |   C   |
| 50–59 |   D   |
|  < 50 |   F   |

The program was tested using the following scores:

```text
91, 76, 64, 52, 43
```

### Screenshot

![Output through screenshots](/home/maurice/screenshot/pic1.png)
![Output through screenshots](/home/maurice/screenshot/pic2.png)
![Output through screenshots](/home/maurice/screenshot/pic3.png)
![Output through screenshots](/home/maurice/screenshot/pic4.png)
![Output through screenshots](/home/maurice/screenshot/pic5.png)
---

## Exercise 1.2 — Combined Conditions

A course is considered **Validated** when:

```text
score >= 50
AND
attendance >= 75
```

Otherwise, the program identifies whether the student has low attendance or has failed.

The test cases were:

```text
(76, 92)
(76, 68)
(43, 95)
```


---

## Question 1.3 — Think About It

The exercise demonstrates why the order of conditions in an `elif` ladder is important.

If `elif score >= 50` comes before `elif score >= 70`, scores of 70 or higher would be caught by the first condition and incorrectly classified before the more specific condition is reached.

---

# Part 2 — Loops & the Accumulator

The following list of scores was provided for Part 2:

```python
[72, 85, 91, 64, 78, 47, 88, 55, 93, 61]
```

## Exercise 2.1 — Loop + Filter

A `for` loop is used to print only scores greater than or equal to 80.

The required output format is:

```text
Top score: X
```
---

## Exercise 2.2 — Accumulator Pattern

A loop is used to calculate:

* Total score
* Number of scores
* Average score
* Number of passed scores
* Number of failed scores

The exercise is completed without using:

```python
sum()
len()
max()
```


---

## Exercise 2.3 — While Loop

A `while` loop is used to calculate how many months are required to save **15,000 RWF per month** toward a **250,000 RWF laptop**.

The loop is designed to stop when the savings reach or exceed the target amount.


---

# Part 3 — Functions

## Exercise 3.1 — `get_grade()`

The grading ladder from Part 1 is converted into a reusable function:

```python
get_grade(score)
```

The function returns the appropriate letter grade.

The function was tested using:

```text
91
76
43
```


---

## Exercise 3.2 — `pass_rate()`

A function named:

```python
pass_rate(score_list)
```

is used to calculate the percentage of scores that are greater than or equal to 50.

For the provided Part 2 scores, the expected pass rate is:

```text
90.0%


---

# Part 4 — Reading the CSV File

## Exercise 4.1 — First Contact

The `week3_students.csv` file is opened using:

```python
with open(...) as f:
```

and the contents are read using:

```python
readlines()
```

The program displays:

* Number of lines
* Header line
* First student's line

The file contains **41 lines** because there are 40 student records plus one header line.

---

## Exercise 4.2 — Extract a Column

Each student record is processed using:

```python
.strip().split(",")
```

The student's name is extracted from index `1` and stored in a list named:

```python
names
```

The program confirms that there are **40 names** and displays the first five names.


---

# Part 5 — The Resilient Pipeline

This is the main data-processing section of the lab.

The dataset contains three records with broken score values. Instead of allowing these records to stop the program, exception handling is used to identify and skip the invalid scores.

---

## Exercise 5.1 — Survive the Mess

The program attempts to convert each score into an integer:

```python
int(parts[7])
```

If the conversion fails, a `ValueError` is handled using `try` and `except`.

The program records:

* Number of valid scores
* Number of bad records
* IDs of the bad records
* Average of valid scores

### Broken Records

The three invalid records are:

| Student ID | Student              | Problem                   |
| ---------- | -------------------- | ------------------------- |
| AUCA008    | Emmanuel Nsengiyumva | Invalid/non-numeric score |
| AUCA020    | Samuel Rukundo       | Missing score             |
| AUCA032    | Gilbert Uwituze      | Invalid/non-numeric score |

The pipeline therefore processes the valid records while surviving the three broken records.


---

## Exercise 5.2 — Grades & the Top Student

Among valid records, the program calculates:

* Number of passed students
* Number of failed students
* Highest score
* Name of the student with the highest score
* Letter grade of the top student

Two accumulators are used:

```python
best_score = -1
best_name = ""
```


## Exercise 5.3 — Report by District

Dictionary accumulators are used to calculate the average score for each district.

The dictionaries follow the pattern:

```python
sums[d] = sums.get(d, 0) + s
counts[d] = counts.get(d, 0) + 1
```

The program then calculates and displays the average score for every district and identifies the district with the highest average.

The dataset contains **8 districts**, with 5 students per district.


# Bonus — First Output File

For the bonus exercise, the program creates:

```text
week3_report.txt
```

The report contains:

* Student count
* Valid records
* Bad records
* Average score
* Top student

The file is then opened again and its contents are printed.

---

# Part 6 — Reflection

## 1. When would I stop trusting the dataset?

The pipeline skipped 3 broken records out of 40, which represents 7.5%.

There is no single percentage that applies to every dataset, because the acceptable level of missing or invalid data depends on the purpose and importance of the data. If the percentage became high enough to significantly affect the analysis, I would stop simply skipping records. Instead, I would investigate the source of the errors, correct the original data if possible, or request a cleaned dataset.

## 2. What surprised or confused me?

One thing I found interesting was how `try` and `except` allow a program to continue processing data even when individual records contain invalid values. Instead of the entire program stopping because of one bad score, the program can identify the problematic record and continue processing the valid records.

---

# Key Python Concepts Practiced

During this lab, I practiced the following concepts:

```text
if / elif / else
for loops
while loops
accumulators
functions
lists
dictionaries
file handling
CSV processing
try / except
ValueError handling
data validation
```

These concepts are useful when working with real-world datasets because real data may contain missing, incorrect, or unexpected values.

---

# How to Run the Project

## 1. Clone the repository

```bash
git clone https://github.com/Big-Data-Group-A/Week3_BYIRINGIRO_Maurice_28216/edit/main/README.md
```

## 2. Enter the project directory

```bash
cd Week3-Lab
```

## 3. Start Jupyter Notebook

```bash
jupyter notebook
```

## 4. Open the notebook

Open:

```text
Week3_BYIRINGIRO_Maurice.ipynb
```

## 5. Make sure the dataset is available

The following files should be in the appropriate project directory:

```text
week3_students.csv
Week3_BYIRINGIRO_Maurice.ipynb
```

## 6. Run the notebook

Run the cells from **Part 1** through **Part 6** in order.

---

--- data analysis.

  


  
