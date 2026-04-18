# Product Data Cleaning & SEO Optimization Project

##  Introduction
This repository documents the end-to-end data transformation of a raw marketing dataset consisting of **3,847 product entries**. The project addresses a critical business challenge: transforming "noisy," inconsistent, and fragmented data into a structured, high-fidelity asset. By transitioning from simple data exploration to rigorous remediation, this project ensures the data is mathematically sound and ready for SEO deployment.

##  Project Objectives
The primary goal was to establish a "Single Source of Truth" for product marketing data through four key pillars:
* **Data Integrity:** Identifying and purging **306 redundant records** to prevent metric inflation.
* **Attribute Remediation:** Systematically resolving high null counts (e.g., **55% missing descriptions**) to ensure dataset completeness.
* **Structural Standardization:** Transitioning from "General" Excel formats to precise **Text** and **Integer** data types to prevent data corruption.
* **Strategic Feature Engineering:** Developing a scalable **short_title** logic to maximize SEO visibility and user scannability.

## Repository Structure
* **`data/`**
    * `productdata_raw.xlsx`: The original, unrefined dataset with duplicates and formatting inconsistencies.
    * `productdata_cleaned.xlsx`: The final, analysis-ready version with standardized headers and optimized titles.
* **`documentation/`**
    * `Aisha_Abdulkarim_Technical_Report.docx`: A professional document detailing the technical methodology and quality audit.
    * `Process_Walkthrough.docx`: A rich, step-by-step guide illustrating the exact Excel formulas and logical steps taken.

## Technical Methodology

### 1. Advanced Cleaning & Remediation
* **Expanding Range Logic:** Implemented a dynamic `COUNTIF($A$2:A2, A2)` formula to isolate duplicates without losing the master record.
* **Placeholder Logic:** Used `IF()` functions to maintain row integrity by filling gaps with "Data Not Available" markers.
* **Precision Engineering:** Converted `product_id` to **String** to preserve essential leading zeros and standardized dimensions to **2 decimal places**.

### 2. Feature Engineering: short_title
I developed a multi-layer nested formula to automate SEO title creation at scale:

**The Formula:**
`=LEFT(TRIM(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(B2, "Set of ", ""), "includes ", ""), "features ", ""), "| ", "- "), "PCS", "")), 47) & IF(LEN(TRIM(...))>47, "...", "")`

* **Noise Filtering:** Programmatically removed promotional fluff (e.g., "Set of", "includes").
* **Visual Polish:** Standardized delimiters (swapping `|` for `-`) and applied **Smart Truncation** with an automated ellipsis (`...`) for professional UI/UX.

## Impact Metrics
| Quality Metric | Pre-Cleaning | Post-Cleaning (Refined) | Impact Improvement |
| :--- | :--- | :--- | :--- |
| **Record Uniqueness** | 306 Duplicates | **100% Unique IDs** | Removed data inflation |
| **Data Types** | Mixed / General | **Standardized** | Ensured formula stability |
| **SEO Readiness** | 0% Optimized | **100% Optimized** | Enhanced brand visibility |
| **Missing Values** | 4,000+ Gaps | **0 Unresolved** | Strategic placeholders used |


---
**Prepared by:** Aisha Abdulkarim  
**Contact:** [aishaabdulkarim738@gmail.com]
