# pubmed-paper-fetcher
This project is a Python-based tool that fetches research papers from PubMed based on a user-defined query and filters out those with at least one *non-academic author* affiliated with a *pharmaceutical or biotech company*.

---

## ✅ Features

- Fetches papers using PubMed API (NCBI E-utilities)
- Filters authors based on institutional affiliation
- Identifies companies based on keywords like pharma, biotech, therapeutics, etc.
- Extracts:
  - PubMed ID
  - Title
  - Publication Year
  - Corporate-affiliated author names
  - Company affiliations
  - Corresponding author’s email
- Saves results as a .csv file

---

## 🧪 Environment

This project was developed and tested using:

- *Python 3.8+*
- *Google Colab* (for execution)
- *No external libraries* (besides requests)

---

## 🚀 How to Use (Google Colab)

### 1. Clone or open this notebook in Colab.

### 2. Paste the module code into a cell (provided in module.py)

### 3. In a new cell, run the following:

```python
from pubmed_fetcher.module import gather_papers, export_to_csv

query = "COVID-19 vaccine"  # Replace with your desired search term
results = gather_papers(query, debug=True)

if results:
    export_to_csv("pubmed_results.csv", results)
    print("✅ CSV generated.")
else:
    print("❌ No qualifying papers found.")
