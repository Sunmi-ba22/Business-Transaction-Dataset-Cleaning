# Business Transaction Data Cleaning Project

### Overview

This project focuses on cleaning and preprocessing a messy business transaction dataset to make it suitable for analysis and downstream machine learning tasks.

Real-world data is rarely clean, and this dataset reflects exactly that. It contains inconsistencies, missing values, distorted entries, and structural issues that required careful handling.

The goal of this project was to transform raw, unreliable data into a structured, analysis-ready dataset while preserving business logic and data integrity.
 ### Dataset Description
Initial Records: 213 rows
Features: 20 columns
Domain: Financial / Business Transactions
Key Issues Identified:
Inconsistent transaction and invoice formats
Misaligned (shifted) rows
Mixed and invalid date formats
Missing values across multiple columns
High sparsity in certain features
Duplicate records

# Data Cleaning Process


## 1. Initial Inspection
Loaded dataset using Pandas
Assessed structure using .shape, .info(), .head()
Identified data quality issues and inconsistencies
## 2. Handling Shifted Rows

Some rows had values incorrectly placed across columns (e.g., dates appearing in the customer name column).

Used regex pattern matching to detect invalid entries
Removed corrupted rows to restore structural consistency

 Result: Dataset integrity significantly improved

## 3. Removing Duplicates
Checked for duplicate records using .duplicated()
Removed exact duplicates

 Result:

Reduced dataset to 202 unique records
Eliminated redundancy that could bias analysis

## 4. Fixing Date Inconsistencies
Converted date column using pd.to_datetime()
Identified large number of unparseable values (NaT)

 Decision:

Dropped the Date column due to excessive invalid entries

## 5. Missing Value Analysis
Calculated missing value percentages
Identified high-null columns
Actions Taken:
Dropped Notes column (>30% missing values)
Retained other columns for imputation
## 6. Imputation Strategy

To preserve data distribution:

Numerical Columns: Filled using median
Categorical Columns: Filled using mode

Why?

Median is robust to outliers
Mode preserves categorical consistency

 Result: No missing values remaining

## 7. Handling Distorted Columns
Identified inconsistencies in:
Transaction ID
Invoice Number
Standardized formats for consistency and usability

## 8. Feature Engineering (Sparse Columns)
Columns with excessive zeros were transformed into binary indicators
(e.g., feature exists vs not exists)

Why this matters:

Preserves useful signal
Improves model interpretability
Reduces noise

## Final Output

Clean, structured dataset
No missing values
No duplicates
Consistent formatting across features
Ready for:
Exploratory Data Analysis (EDA)
Machine Learning models

## Key Skills Demonstrated

This project highlights strong practical skills in:

Data Cleaning & Preprocessing
Handling Missing Data
Feature Engineering
Data Validation & Integrity Checks
Pandas & Python Data Manipulation
Problem-solving with messy real-world data

## Key Takeaways
Real-world datasets are messy, cleaning is not optional, it’s critical
Decisions like dropping vs imputing require context, not guesswork
Preserving business logic is just as important as technical correctness

 ## Tools & Technologies
Python
Pandas
NumPy
Regular Expressions (re)

 ## Author

Sunmisola Lawal


Data Scientist | Machine Learning Engineer

