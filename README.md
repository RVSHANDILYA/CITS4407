# CITS4407 Assignment 2  
**“Board Games or Bored Games?”**  

**Version:** 1.0  

**Date:** 19 May 2025  

**Name:** Raja Venkata Shandilya Puram

**Student ID** 24944809

**Course:** CITS4407 – Data Processing in the Unix Environment  

---

## 📂 Repository Contents

- `empty_cells`  
  Counts empty cells in each column of a delimiter-separated file.
- `preprocess`  
  Cleans a `;`-delimited dataset: converts to TSV, normalizes line endings, fixes decimals, removes non-ASCII, fills missing IDs.
- `analysis`  
  Answers the four research questions on the cleaned dataset (most popular mechanics, domains, and two Pearson correlations).
- `README.md`  
  This file.

---

## 🚀 Prerequisites

- A Unix‐like environment (Linux, macOS, or WSL).  
- Bash shell (`/usr/bin/env bash`).  
- Standard Unix tools: `awk`, `sed`, `tr`, `tail`, `head`.  
- No external libraries or interpreters required.

---

## ⚙️ How to Run

1. **Make all scripts executable**  
   ```bash
   chmod +x empty_cells preprocess analysis
2. **Count empty cells**  
   ```bash
   ./empty_cells bgg_dataset.txt ";"
3. **Preprocess / clean
   ```bash
   ./preprocess bgg_dataset.txt > cleaned_bgg_dataset.tsv
4. **Analyze**
   ```bash
   ./analysis cleaned_bgg_dataset.tsv

## 🧪 Testing & Corner cases

 `empty_cells`
- Empty file → error and exit.
- Header-only → prints zero counts.
- Whitespace-only fields → counted as empty.
- Blank lines → count as empty for every column.
- Wrong delimiter → errors out if only one column detected.
- Non-ASCII → stripped before counting.

 `preprocess`

- Fills missing IDs by scanning max existing ID.
- Leaves mechanics/domain commas intact.
- Handles mixed line endings and non-ASCII safely.
- Converts comma-decimals to dot-decimals.
- Replaces semicolons with tabs for TSV.

`analysis`
- Ignores rows with missing mechanics or domains when counting popularity.

- Calculates Pearson correlation for numeric fields.
