MK EAE Response Viewer – User Guide

**Overview:** The MK EAE Response Viewer is a browser-based tool that fetches event metadata from two MediaKind endpoints (DCG and DCH) and presents it side-by-side for quick inspection, searching, and export.

Link: [https://bhavesh-ses.github.io/SES_EventViewer/](https://bhavesh-ses.github.io/SES_EventViewer/)

**Layout & Controls**

**Element**

**Description**

**Search Box**

Located at the top. Filters both DCG & DCH tables in real-time as you type. Type any text (e.g. OAID, Region, Description snippet) to narrow the visible rows.

**Export DCG**

Downloads the currently displayed DCG table as an Excel file (DCG_Events.xlsx). Only active (visible) rows are included.

**Export DCH**

Downloads the currently displayed DCH table as an Excel file (DCH_Events.xlsx). Only active (visible) rows are included.

**DCG Container**

Shows the DCG events table. Automatically populated on page load (and refreshed by reload). If the fetch fails, an error message appears here.

**DCH Container**

Shows the DCH events table. Automatically populated on page load (and refreshed by reload). If the fetch fails, an error message appears here.

**Step-by-Step Usage**

1.  **Open the Tool** Simply open index.html in any modern browser. The page immediately begins fetching DCG and DCH data.
2.  **Wait for Data to Load**

- **“Loading…”** placeholders appear until each region’s data arrives.
- On success, a table appears showing each event’s key fields (OAID, start/end times, type, regions, description, captions, etc.).
- On failure, you’ll see an error message in place of the table.

1.  **Search**

- Click into the **Search Box** and start typing.
- The tables update live, hiding any row that does not contain your term in any column.
- Clear the box to restore all rows.

1.  **Export to Excel**

- After filtering or searching, click **Export DCG** or **Export DCH** to download the visible rows for that region.
- The downloaded .xlsx file preserves column headers and current row order.

**Button & Control Details**

- **Search Box**
- **What it does:** Filters both tables simultaneously.
- **Options/Interactions:** Type any substring (case-insensitive). Wildcards not supported—just plain text.
- **Limitations:** Very large datasets (thousands of rows) may slow the browser.
- **Export DCG / Export DCH**
- **What it does:** Converts the active table into an Excel worksheet.
- **Options/Interactions:** One click per region. Cannot export both at once.
- **Limitations:** Exports only rows currently visible—hidden rows due to search are excluded.
- **Automatic Data Fetch on Load**
- **What it does:** On page open (or reload), the tool issues GET requests to both endpoints.
- **Options/Interactions:** No manual “Refresh” button—simply reload the page to fetch fresh data.
- **Limitations:** Requires network access to the API endpoints; errors (network/CORS) will be shown inline.

**Working Logic (High-Level)**

- **Data Retrieval:** Issue parallel fetches to DCG and DCH event endpoints.
- **Data Transformation:** Extract and normalize nested fields (e.g., OAID, times, descriptions, sources).
- **Rendering:** Dynamically build HTML tables with consistent column order.
- **Searching:** Debounced, client-side filter that hides non-matching rows.
- **Exporting:** Utilize SheetJS to generate and download .xlsx files from JavaScript arrays.

**Known Limitations & Best Practices**

- **Data Volume:** Very large result sets (5,000+ rows) may degrade performance. Consider pre-filtering at the API level if possible.
- **Description Truncation:** Long descriptions are trimmed to 150 characters for readability. Full text is visible on hover (via cell tooltip).
- **No Persistent Filters:** Search and filtering are session-only. Reload or navigate away resets state.
- **Unsupported Browsers:** Requires a modern browser (Chrome, Firefox, Edge).
