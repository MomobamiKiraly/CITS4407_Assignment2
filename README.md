# CITS4407_Assignment2 of Board Game Dataset

Author: Chi Zhang
Student ID: 23954248  

This project contains three Bash scripts for handling and analyzing a board game dataset (originally sourced from BoardGameGeek). Each script is designed to perform a specific function in the data processing workflow: detecting missing values, cleaning raw data, and performing analysis.

---

## Script Overview

### 1. `empty_cells`

**What it does**:  
Checks how many empty cells are in each column of a semicolon-separated file. It reads the header to get the column names and counts the blanks line by line.

**How to run**:
```bash
./empty_cells sample1.txt ";"
```

You’ll get output like:
```
/ID: 1
Name: 0
Mechanics: 3
...
```

---

### 2. `preprocess`

**What it does**:  
Cleans the raw dataset and prints the result to standard output. It replaces `;` with tabs, converts Windows line endings to Unix style, replaces decimal commas with dots, strips out non-ASCII characters, and fills in missing `/ID` fields with new IDs.

**How to run**:
```bash
./preprocess sample1.txt
```

The cleaned version of the file will appear in your terminal. You can redirect it to a file if needed:
```bash
./preprocess sample1.txt > sample1_cleaned.tsv
```

---

### 3. `analysis`

**What it does**:  
Analyzes the cleaned data to answer four questions:
- What’s the most common game mechanic?
- What’s the most common domain?
- Is there a correlation between year and rating?
- Is there a correlation between complexity and rating?

**How to run**:
```bash
./analysis cleaned_bgg_dataset.tsv
```

Expected output looks like:
```
The most popular game mechanics is   5672 Dice Rolling
The most popular game domain is      3316 Wargames
The correlation between the year of publication and the average rating is 0.081
The correlation between the complexity of a game and its average rating is 0.481
```

---

## Notes

- All scripts assume tabular text input with a consistent column order.
- Tested on Git Bash for Windows.
- No external dependencies required (uses standard Unix tools).
