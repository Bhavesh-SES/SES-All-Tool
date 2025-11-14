# JSON Variant Compare Tool — User Guide

🔗 **Live Tool:** https://bhavesh-ses.github.io/JSON-Variant-Compare-Tool/

---

## Overview

The **JSON Variant Compare Tool** enables fast, side-by-side comparison of JSON variant configurations (for example, “dazn-latin” vs. “global”) across multiple environments. Paste one JSON per line or upload a CSV, and the tool instantly highlights:

- 🟩 **Matching fields** — shown in green  
- 🟥 **Mismatches** — shown in red

With **live search**, **full-tree expand/collapse**, and **Excel export**, spotting and reconciling configuration differences becomes quick and effortless.

---

## 1. Theme Toggle

**Button:** `Toggle Theme`

- Switches between **light** and **dark** modes  
- Helpful for long sessions or different lighting conditions  
- No limitations

---

## 2. Mode Selector

**Dropdown Options:** `Paste JSON` / `Upload CSV`

### Paste JSON Mode
- Displays two panels:
  1. **Paste Nested JSON** — Paste **one JSON object per line**. Each line must be valid JSON.
  2. **Sorted Output** — Shows sorted values extracted from each JSON in real time and provides a **Copy** button.
- **Limitation:** Best for small–medium datasets (a few dozen lines). Very large inputs may slow the browser.

### Upload CSV Mode
- Shows a **file picker** and the **full comparison table**.
- **CSV Requirements:** Header row **must be exactly**:

OverRideID,DCA,DCB,DCC,DCD
Each `DCA`–`DCD` cell must contain a valid JSON string.
- **Limitation:** Extremely large CSVs (>5,000 rows) may take several seconds to parse.

---

## 3. Paste Mode Controls

- **JSON Input Box**  
Placeholder: _“Paste your JSON rows here (one per line)…”_  
Each line must be a valid JSON object.

- **Load Pasted JSON**  
Converts each pasted line into a comparison row and auto-generates `OverRideID` values like **Row 1**, **Row 2**, etc.

- **Sorted Output Copy**  
Copies comma-separated sorted values (one line per JSON) to clipboard for reuse.

---

## 4. Upload Mode Controls

1. **File Picker** — Select a `.csv` file.

2. **Load CSV** — Parses the CSV and renders the comparison table (requires exact headers). Invalid/malformed rows are flagged.

3. **Download XLSX** — Export the displayed table to `comparison.xlsx`, preserving match/mismatch coloring.

4. **Search Box**
   - Filters rows dynamically (live filtering as you type).
   - Highlights matched text in **yellow**.
   - Case-insensitive substring matching; clear the box to restore the full table.

5. **Expand All (➕) / Collapse All (➖)**
   - **Expand All:** Fully expands every JSON tree.
   - **Collapse All:** Minimizes JSON to single-line summary.
   - Works any time, before or after a search.

---

## 5. Table Behavior & Legend

- **Columns**
- **OverRideID** — Unique ID from CSV or auto-generated.
- **DCA / DCB / DCC / DCD** — Each displays a collapsible nested JSON tree.

- **Match Coloring**
| Color | Meaning |
|-------|---------|
| 🟩 Green | Exact match with `DCA` |
| 🟥 Red   | Mismatch from `DCA` |
| ⚪ White | Reference column (`DCA`) baseline |

- **Scrolling** — Tall JSON trees scroll inside their cell.
- **Limitations**
- Very deeply nested JSON (>10 levels) may not fully expand automatically.
- Invalid JSON cells display **“Invalid JSON”**.

---

## 6. Typical Workflow

1. **Choose mode** — Paste JSON (small snippets) or Upload CSV (bulk).
2. **Provide input** — Paste objects (one per line) or select a CSV file.
3. **Load data** — Click **Load Pasted JSON** or **Load CSV**.
4. **Explore**
 - Use **Search** to find keys/values or IDs.
 - **Expand/Collapse** JSON trees.
 - Inspect green/red differences.
5. **Export** — Click **Download XLSX** to save the comparison with color indicators.

---

## Tips & Notes

- Use **Paste JSON** for quick checks; **Upload CSV** for bulk comparisons.
- Split very large CSVs (5k+ rows) to improve performance.
- Search is **case-insensitive** and highlights exact substring matches.
- Hover inside cells to scroll long lists.
- Theme toggle helps readability during long sessions.
