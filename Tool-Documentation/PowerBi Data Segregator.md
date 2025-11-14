# **PowerBI Export Filterer – User Guide**

## **Purpose**
The **PowerBI Export Filterer** is a browser-based utility that allows users to **load PowerBI-exported CSV/XLSX datasets**, apply advanced **search, filters, date rules**, review the cleaned dataset in a **dynamic table**, and export the filtered results into a clean, formatted Excel workbook.

It is designed specifically for operations teams who frequently receive PowerBI raw dumps and need a faster way to filter, slice, export, and share cleaned data without manually applying Excel filters every time.

This tool makes data review **faster, consistent, accurate, and shareable**.

**Tool Link:** https://bhavesh-ses.github.io/PowerBi_Data_Filter_Tool/


---

## **Overview**
Once a PowerBI dataset is uploaded, the tool provides:

- A **smart auto-formatted table** with adjustable column widths  
- **Powerful multi-search bar** for finding any text  
- **Date filtering panel** (Single date / Before / After / Between)  
- **Filter groups** (with AND/OR logic)  
- **Real-time matching row count**  
- **Excel export with filters applied**  
- Automatic handling of **UTC date/time columns**  
- Column resizing with **drag resizers**  
- Fully responsive layout with horizontal scroll support

It requires **no installation or backend** — everything runs in your browser.

---

## **Why This Tool Is Useful**
Operators often receive large PowerBI exports with thousands of rows. Cleaning these manually is slow, inconsistent, and error-prone.

PowerBI Export Filterer solves this by providing:

1. **Fast Upload & Instant Table Preview**  
   Upload a PowerBI sheet and immediately see structured data in a searchable table.

2. **Deep Filtering Options**  
   Combine quick-search + multiple filters + date filters without modifying source data.

3. **Accurate Exports**  
   The exported Excel includes **exactly what you filtered**, ensuring consistent reporting.

4. **Timezone-Safe Date Handling**  
   Dates are normalized in **UTC** for operational accuracy.

5. **Operational Repeatability**  
   Once filters are set, the tool becomes a standardized data-cleaning workflow.

6. **Zero Installation**  
   Works directly in a browser — great for operations, shift teams, analysts, and reporting.

---

## **Getting Started**

### **Step 1: Upload the PowerBI File**
- Click the **Upload File** button.
- Choose a `.csv` or `.xlsx` exported from PowerBI.
- Once uploaded:
  - Columns are auto-detected.
  - The table loads instantly with pagination and search.

> *Tip: If your PowerBI report exports multiple sheets, ensure you upload the correct sheet containing your events/logs/metrics.*

---

## **Step 2: Explore the Data Table**
The main table supports:

- **Horizontal scroll**  
- **Sort per column**  
- **Pagination (10–250 rows per page)**  
- **Resizable columns** (drag from header edge)  
- **Auto-width calculation** to match content  
- **Real-time updates** whenever filters change  

> *You can adjust column width from the header or choose auto-size to let the tool fit data.*

---

## **Step 3: Use Global Search**
At the top of the table:

- Type any keyword  
- The entire dataset filters instantly  
- Multi-column matching is supported  
- Case-insensitive search  

Useful when looking for:
- OAID  
- Channel Name  
- Event titles  

---

## **Step 4: Use the Filter Panel**

Click **Filters** to open the Filter Panel.

You'll see:

### **A) Multiple Filters**
Each filter has:
- A label  
- A dropdown (equals / contains / starts with / ends with)  
- A value box  
- A checkbox to enable/disable  

You can:
- Enable multiple filters  
- Choose **AND** mode (all conditions must match)  
- Choose **OR** mode (any condition can match)  

### **B) Live Match Count**
At the top of the panel:
- Shows how many rows match your current filters  
- Updates instantly  

### **C) Add or Remove Filters**
Click **Add Filter** to include more rows  
Click **Remove** to delete a filter  

### **D) Auto-synchronized Table**
Whenever you change anything in filters:
- The table updates immediately  
- No need to press Apply/Submit  

---

## **Step 5: Apply Date Filters**
The tool includes a dedicated **Date Filter** module.

Supported modes:
- **Exact Date**
- **Before date**
- **After date**
- **Between Start & End dates**

Key points:
- Dates are automatically interpreted in **UTC**, matching PowerBI export timestamps  
- Only the selected date column is filtered  
- Combined with text filters using AND/OR logic  

---

## **Step 6: Export to Excel**
When ready, click **Export**.

The exported file includes:
- Only the rows that passed your filters  
- All columns from the uploaded dataset  
- UTC-normalized date values  
- Clean headers  
- Sheet per filter group (when OR mode is selected)  
- A unified sheet called “All” when no filters are selected  

File name example:  
`filtered_export_2025-01-31_14-20-05.xlsx`

> *Export respects all active filters, date rules, search box, and pagination does not affect export.*

---

## **Step 7: Column Resizing**
You can resize columns in two ways:

### **Auto Column Sizing**
Automatically adjusts widths based on:
- Header length  
- Cell content  
- Maximum width limits  

### **Manual Resizing**
- Move your cursor to the right edge of the header  
- Drag to increase/decrease width  
- Both header and rows resize together  
- Works smoothly even with horizontal scrolling  

---

## **Additional Features**

### **Real-Time Filtering**
Filtering is instant — no apply buttons.

### **Responsive Layout**
The table adjusts to:
- Large monitors  
- Smaller laptops  
- Embedded views  

### **Scroll-Sync**
The header and rows scroll perfectly aligned horizontally.

### **Filter Mode Toggle**
Switch between:
- **AND** → strict filtering  
- **OR** → multi-group export  

### **Instant Table Refresh**
When uploading a new sheet:
- Previous data is cleared  
- All filters reset automatically  

---

## **Best Practices & Tips**

### **Before Using**
- Ensure your PowerBI file is exported in CSV/XLSX  
- Validate date formats (UTC preferred)  
- Remove empty rows in PowerBI before export  

### **During Use**
- Use the search bar for fast text matching  
- Use date filters for time-based slicing  
- Resize columns to improve readability  
- Enable AND mode for precise filtering  
- Use OR mode to export separate sheets per filter  

### **After Export**
- Share the filtered Excel with your team  
- Use the export file as your shift or incident report attachment  
- Keep original PowerBI dump for audit  

---

## **How It Helps Operations Teams**

| Operational Need | How the Tool Solves It |
|------------------|------------------------|
| Quick filtering of large PowerBI exports | Dynamic filters, search, date rules |
| Consistent reporting | Standardized Excel export |
| Fast investigation | Search instantly across thousands of rows |
| Shift handover | Export clean sheets for sharing |
| Reduce manual Excel work | Automated filter & export system |

---

## **In Summary**
The **PowerBI Export Filterer** transforms how operations teams review PowerBI datasets:

- **No Excel filter hassles**  
- **No manual cleanup**  
- **No formula errors**  
- **No timezone mismatches**  

It provides:
- Clean UI  
- Instant filtering  
- Smart date handling  
- Reliable Excel outputs  

Whether you're performing daily health checks, log validation, event-based investigations, or shift reporting, this tool ensures you always get **accurate, clean, and operationally useful** data exports.

---

## **File Formats Supported**
- `.csv`  
- `.xlsx`  

