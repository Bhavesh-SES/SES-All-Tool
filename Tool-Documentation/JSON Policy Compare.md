JSON-Policy-Compare Tool — User Guide

**Overview:** The JSON-Policy-Compare Tool lets you quickly compare and validate JSON-encoded policy or variant configurations across multiple data sources (e.g., DCA, DCB, DCC, DCD). Whether you paste individual JSON lines or upload a CSV, the tool highlights exact matches in green, discrepancies in red, and supports live search, full-tree expand/collapse, and Excel export—making it effortless to spot and reconcile differences.

Link: [https://bhavesh-ses.github.io/JSON-Policy-Compare-Tool/](https://bhavesh-ses.github.io/JSON-Policy-Compare-Tool/)

**1\. Theme Toggle**

**Button:** Toggle Theme

- **What it does:** Switches between light-mode and dark-mode color schemes.
- **When to use:** If you’re working in low-light (dark) or bright environments (light).
- **Limitations:** None.

**2\. Mode Selector**

**Control:** Paste JSON / Upload CSV

- **Paste JSON**
- **What it shows:** Two side-by-side boxes.

1.  **“Paste Nested JSON”** — Paste (or type) one JSON array per line.
2.  **“Sorted Output”** — Immediately shows each line’s sorted values.

- **Use case:** Quickly test or transform a handful of JSON arrays.
- **Upload CSV**
- **What it shows:** CSV uploader and a data table.
- **Use case:** Compare large data sets in bulk.

**3\. Paste Mode Controls**

- **JSON Input Box**
- **Placeholder:** “One JSON array per line”
- **Tip:** Ensure each line is valid JSON (an array of {"S":"…"} objects).
- **Sorted Output**
- **Auto-update:** As soon as you type or paste.
- **Copy Button:** Copies the plain sorted values (one line per JSON).

**Restrictions:**

- Malformed JSON → marked with “Invalid JSON”
- Deeply nested or extremely large arrays may take a moment to sort.

**4\. Upload Mode Controls**

1.  **File Picker (“Upload CSV”)**

- Accepts .csv only.
- **Expected columns:**
- **OverRideID** — any identifier (ignored in sorting).
- **DCA–DCD** — each must contain a JSON array like \[{"S":"foo"},…\].

1.  **Load & Process**

- Parses CSV, extracts “S” values from each JSON column, sorts them, and displays a table.

1.  **Download CSV**

- Exports the processed table (including sorted values and match/mismatch color coding) as output.csv.

1.  **Search Box**

- Filters rows live by matching **any column** (ID or sorted values).
- **Exact-word highlight**: only the matched substring is highlighted.
- **Clearing** the box restores the full table and removes highlights.

1.  **Expand/Collapse All (➕ / ➖)**

- Expand (**➕**) shows full sorted lists in each cell (no clipping).
- Collapse (**➖**) truncates or hides overflow for a compact view.

**Restrictions & Tips:**

- CSV must have a header row exactly matching:

OverRideID,DCA,DCB,DCC,DCD

- Each JSON cell must parse to an array of objects with key "S".
- Large CSVs (thousands of rows) may load slowly—consider breaking them into smaller chunks.
- Search is case-insensitive but exact: partial matches will still highlight only the matched substring.

**5\. Table Output**

- **Green cells** (match): values exactly match the first column (DCA).
- **Red cells** (mismatch): any deviation from DCA.
- **Hover tip:** you can scroll within any cell if the sorted list overflows.

**Quick–Start Workflow**

1.  **Choose your mode** (Paste vs Upload).
2.  **Provide your input**: paste JSON lines or select a CSV.
3.  **Click “Load & Process”** (upload mode) or watch the output update live (paste mode).
4.  **Search** if you need to filter down to specific IDs or values.
5.  **Use Expand/Collapse** to adjust table density.
6.  **Download** your final CSV for archiving or further analysis.
