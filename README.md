# HDB Resale ETL Pipeline

## Overview

This repository contains my submission for the Data Engineer technical assessment.

The notebook demonstrates an end-to-end ETL pipeline using the Singapore Data.gov.sg HDB resale API. The solution follows a layered architecture consisting of Bronze, Silver and Gold data layers, with data quality validation, business transformations, audit reporting and output generation.

The implementation emphasises readability, maintainability, auditability and traceability through clearly separated pipeline stages, validation checkpoints and inline documentation.

---

![Jupyter Notebook Structure 1](images_and_videos/Overall%20project%20image.png)
![Jupyter Notebook Structure 2](images_and_videos/Overall%20project%20image.png)


## Repository Structure

```
.
├── README.md
├── hdb_resale_pipeline.ipynb
├── output/
│   ├── raw/
│   ├── cleaned/
│   ├── transformed/
│   ├── failed/
│   └── hashed/
```

The output folders will be created automatically when the notebook is executed.

---

## Technologies Used

- Python 3.x
- Pandas
- Requests
- Great Expectations
- Jupyter Notebook

---

## ETL Pipeline

### Bronze Layer

- Retrieve collection metadata
- Extract all child datasets through API pagination
- Audit child dataset schemas
- Validate schema consistency
- Align schemas
- Create Bronze master dataset

### Silver Layer

- Create working dataset
- Clean: Standardise data types
- Clean: Resolve duplicate composite keys
- Clean: Perform basic data standardisation
- Profile: Profile dataset quality
- Profile: Validate source record integrity
- Quality Control: Perform data quality validation using Great Expectations
- Quality Control: Apply quality gate
- Transform: Recompute remaining lease
- Transform: Generate resale identifier
- Transform: Hash resale identifier using SHA-256
- Compare data protection techniques

### Gold Layer

- Strategic Planning dataset (resale price anomaly detection)
- Data Science dataset (January 2012 – December 2016)

---

## Output

The notebook exports the following datasets:

- Raw
- Cleaned
- Transformed
- Failed
- Hashed

All outputs are written to the `output` directory.

Existing output files are overwritten when the notebook is re-executed.

---

## How to Run

### 1. Clone the repository

```bash
git clone <repository-url>
cd <repository-name>
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

or install manually if preferred.

### 3. Launch Jupyter Notebook

```bash
jupyter notebook
```

Open the notebook.

### 4. Execute the notebook

Run all cells from top to bottom.

The notebook will:

- retrieve metadata
- extract all child datasets
- execute the complete ETL pipeline
- generate the Gold datasets
- export all output datasets

No manual folder creation is required.

---

## Notes

- Diagnostic print statements and preview tables are intentionally included to assist code review and validation.
- Output directories are created automatically if they do not already exist.
- The notebook is designed to be executed sequentially from the first cell to the last.
