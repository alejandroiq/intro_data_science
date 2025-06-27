============================================================

INTRODUCTION TO DATA SCIENCE – SUMMARY OF EXERCISES
============================================================

This repository includes conceptual and practical exercises that cover the fundamentals of how data is represented, collected, and described. 
The activities focus on identifying data types, loading structured data (CSV, JSON), and applying statistical summaries to explore central tendencies and variability.

------------------------------------------------------------
PART 1: TYPES OF DATA & DATA COLLECTION
------------------------------------------------------------

- Distinguished between **qualitative (categorical)** and **quantitative (numerical)** data.
- Explored subtypes such as **nominal**, **ordinal**, **discrete**, and **continuous** variables.
- Practiced identifying data types based on context (e.g., survey, sensor, or log data).
- Applied rules to determine the correct classification of a column in a dataset.
- Introduced common methods for **collecting data**, including surveys, experiments, observational studies, and web scraping.
- Compared **probability** vs **non-probability** sampling techniques and when each is appropriate.

------------------------------------------------------------
PART 2: LOADING STRUCTURED DATA – CSV & JSON FORMATS
------------------------------------------------------------

- Worked with **CSV (Comma-Separated Values)** files as a default tabular format.
- Loaded CSV files using `pandas.read_csv()` and explored options like setting headers and parsing columns.
- Reviewed real-world examples of tabular data loading, such as loading population data or sports statistics.
- Introduced the **JSON (JavaScript Object Notation)** format for semi-structured data.
- Practiced navigating and parsing nested structures within JSON objects using Python and Pandas (`json.loads`, `pd.json_normalize`).

------------------------------------------------------------
PART 3: STATISTICAL MEASURES – CENTER AND SPREAD
------------------------------------------------------------

- Computed **measures of central tendency**: mean, median, and mode.
- Applied each based on context (e.g., using **median** for skewed distributions).
- Practiced summarizing datasets with `.mean()`, `.median()`, and `.mode()` in Pandas.
- Calculated **measures of dispersion**: range, interquartile range (IQR), variance, and standard deviation.
- Analyzed how data spread affects interpretation and the reliability of averages.
- Used `.std()` and `.var()` in Pandas and discussed their significance in comparing datasets.

