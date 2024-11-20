# **Amazon Reviews Analysis and Export Workflow**

This repository contains a series of Jupyter Notebooks for processing and analyzing the **McAuley-Lab/Amazon-Reviews-2023 dataset**. These scripts are designed to handle large-scale datasets, split data for efficient processing, and generate summarized insights. The workflow leverages **Pandas**, **DuckDB**, and **Feather** file formats for speed and flexibility.

For the complete results in a beautiful PDF, [just visit Peak Python for the 9 page report.](https://www.peakpython.com/blog/pandas-ibis-performance)
[<img src="Grab_the_report_at_Peak_Python_com_blog_pandas-ibis-performance.png" width="800" />](https://www.peakpython.com/blog/pandas-ibis-performance)

We will use similar data for our new course, [**Rethinking Python Pandas: 5x-100x Speed & Maximum Flexibility with Python Ibis**](https://www.peakpython.com/rethinking-python-pandas-10x-speed-flexibility-with-python-ibis).

---

## **Notebooks Overview**

### **002_read_CSV_export.ipynb**
- **Purpose**: 
  - Reads the CSV file of Amazon Reviews into a DataFrame.
  - Exports data to:
    1. **DuckDB**: For later processing with **Ibis**.
    2. **Feather**: For ultra-fast access with **Pandas**.
- **Setup**:
  1. Create `duckdb` and `feather` directories.
  2. Update the `core_path` variable.
- **Author**: [Stephen McDaniel](https://PeakPython.com)  
- **License**: MIT License

---

### **003a_split_feather.ipynb**
- **Purpose**:
  - Reads the Feather file.
  - Splits data into:
    1. A Feather file with most columns (excluding large text fields).
    2. A Feather file containing the large text columns.
- **Setup**:
  1. Update the `core_path` variable.
- **Notes**:
  - The `row_number` field is the unique identifier for both files.
- **License**: MIT License

---

### **003b_split_tables_duckdb.ipynb**
- **Purpose**:
  - Reads data from DuckDB.
  - Splits data into:
    1. A table with most columns (excluding large text fields).
    2. A table containing the large text columns.
- **Setup**:
  1. Update the `core_path` variable.
- **License**: MIT License

---

### **004a_read_new_sum_feather.ipynb**
- **Purpose**:
  - Reads the smaller Feather file (step 3a).
  - Generates three summaries:
    1. Grouped by **year**.
    2. Grouped by **year** and **helpful votes**.
    3. Grouped by **year**, **helpful votes**, and **verified purchase** status.
- **Setup**:
  1. Update the `core_path` variable.
- **License**: MIT License

---

### **004b_read_new_sum_duckdb.ipynb**
- **Purpose**:
  - Reads the smaller DuckDB table (step 3b).
  - Produces the same summaries as 004a but uses DuckDB for processing.
- **Setup**:
  1. Update the `core_path` variable.
- **License**: MIT License

---

### **011a_10x_read_new_sum_feather.ipynb**
- **Purpose**:
  - Unions the smaller Feather file (step 3a) **10 times**.
  - Generates the same three summaries as 004a.
- **Setup**:
  1. Update the `core_path` variable.
- **License**: MIT License

---

### **011b_read_new_sum_duckdb.ipynb**
- **Purpose**:
  - Unions the smaller DuckDB table (step 3b) **10 times** as a view.
  - Generates the same three summaries as 004b.
- **Setup**:
  1. Update the `core_path` variable.
- **License**: MIT License

---

## **General Instructions**
1. **Before Running Any Notebook**:
   - Ensure the necessary directories (`duckdb`, `feather`, etc.) are created.
   - Update the `core_path` variable to point to the appropriate directories.

2. **Software Requirements**:
   - Python 3.8+
   - Jupyter Notebook or Jupyter Lab
   - Pandas, DuckDB, and other required libraries (install via `requirements.txt` if provided).

---

## **Acknowledgments**
- **Data Source**: [McAuley-Lab/Amazon-Reviews-2023](https://github.com/Stephen-McDaniel/Download_Amazon_Reviews_2023)
- **Author**: [Stephen McDaniel](https://PeakPython.com)

---

## **License**
This project is licensed under the MIT License.
