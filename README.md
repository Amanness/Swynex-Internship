# Nashville Housing Data Cleaning | Excel

A data cleaning project using Microsoft Excel to clean and prepare the Nashville Housing Sales dataset for further analysis.

The project focuses on identifying and fixing data quality issues such as inconsistent values, missing addresses, duplicate records, extra spaces, and incorrect data formats.

## Dataset Overview

The dataset contains housing sales records from Nashville, Tennessee, covering the period from January 2013 to December 2019.

- **Original Records:** 56,477 rows
- **Cleaned Records:** 56,374 rows
- **Original Columns:** 19
- **Cleaned Columns:** 21

## Tools & Techniques

- Microsoft Excel
- Find & Replace
- TRIM
- IF and XLOOKUP
- Text to Columns
- Remove Duplicates
- Filters and PivotTables

## Data Cleaning Process

### 1. Data Standardization
- Standardized `SoldAsVacant` values by replacing Y/N with Yes/No.
- Corrected inconsistent labels in the `LandUse` column.
- Removed unnecessary spaces from address and name fields using TRIM.

### 2. Handling Missing Values
- Identified 29 missing values in `PropertyAddress`.
- Used XLOOKUP with ParcelID to retrieve missing property addresses from matching records.
- Replaced blank values in name-related columns with `Unknown`.
- Kept missing numerical values blank to avoid introducing misleading data.

### 3. Splitting Address Columns
Used Text to Columns to separate combined address fields:

- `PropertyAddress` → `PropertyStreet`, `PropertyCity`
- `OwnerAddress` → `OwnerStreet`, `OwnerCity`, `OwnerState`

### 4. Duplicate Removal
- Identified duplicate sales records using ParcelID, PropertyAddress, SalePrice, SaleDate, and LegalReference.
- Excluded UniqueID from duplicate identification.
- Removed 103 duplicate records.

### 5. Data Type Correction
- Converted date fields into proper date formats.
- Corrected numerical data types for prices and property values.
- Maintained IDs and reference fields as text.

## Before & After

| Metric | Before | After |
|---|---:|---:|
| Total Rows | 56,477 | 56,374 |
| Total Columns | 19 | 21 |
| SoldAsVacant Values | 4 | 2 |
| Missing Property Addresses | 29 | 0 |
| Duplicate Records | 103 | 0 |
| Address Columns | 2 | 5 |

## Files Included

| File | Description |
|---|---|
| `NashvilleHousingUncleaned.xlsx` | Original dataset |
| `NashvilleHousingCleaned.xlsx` | Cleaned dataset |

## Important Notes

- Missing numerical values were kept blank instead of replacing them with zero or average values.
- `TotalValue` contains zero values that represent unavailable data rather than actual zero property values.
- `TaxDistrict` was removed during cleaning.
- Extreme sale prices were retained for further investigation during analysis.

## Key Learnings

Through this project, I worked on:

- Identifying and handling data quality issues.
- Standardizing inconsistent text values.
- Using lookup formulas to recover missing information.
- Splitting and transforming text columns.
- Identifying and removing duplicate records.
- Correcting data types and validating the cleaned dataset.

This project helped me gain practical experience with Excel data cleaning techniques and understand the importance of preparing reliable data before performing analysis.

## Author

**Aman Alam**
