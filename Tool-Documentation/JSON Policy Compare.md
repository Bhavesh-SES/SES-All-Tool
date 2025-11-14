# JSON-Policy-Compare Tool

The **JSON-Policy-Compare Tool** helps you compare and validate JSON-encoded policy or variant configurations across multiple sources (DCA, DCB, DCC, DCD).  
It highlights exact matches in **green**, mismatches in **red**, supports live search, bulk CSV processing, expand/collapse, and Excel export—making it ideal for debugging and reconciliation workflows.

 **Live Tool:**  https://bhavesh-ses.github.io/JSON-Policy-Compare-Tool/

---

##  Features

###  Compare JSON Arrays  
- Paste nested JSON arrays  
- Upload CSV files with JSON columns  
- Auto-extracts and sorts `"S"` values  
- Highlights matches/mismatches

###  Live Search  
- Filters across all columns  
- Highlights only the matched text  
- Case-insensitive

###  CSV Export  
- Download processed & color-coded CSV  
- Preserves sorted outputs

###  Expand/Collapse View  
- View long arrays fully  
- Collapse them for compact view

###  Theme Toggle  
- Switch between Light/Dark mode instantly

---

##  Modes

### **1. Paste JSON Mode**
- Paste one JSON array per line. Example: [{"S": "a"}, {"S": "b"}]
- The tool will: Parse each line & Extract "S" values
- Sort them
- Show results instantly in the “Sorted Output” section
- Includes a Copy button.

### **2. Upload CSV Mode**
- Upload a .csv file with the following exact columns:
- Copy code
- OverRideID, DCA, DCB, DCC, DCD
- Each JSON column must contain an array of objects:
- Copy code [{"S":"foo"}, {"S":"bar"}]
- The tool: Parses all rows 
- Extracts & sorts "S" values
- Builds a color-coded comparison table
- Allows Search, Expand/Collapse, and CSV Download

### **3. Color Coding**
Color	Meaning
- 🟩 Green	Matches reference (DCA)
- 🟥 Red	Values differ
- ⚪ White	Reference column (baseline)

Quick Start

- Open the tool
- Select Paste JSON
- Paste one JSON array per line
- See instant sorted output
- Copy results if needed

Upload CSV
- Select Upload CSV
- Upload your file
- Click Load & Process
- Review color-coded table
- Search or Expand/Collapse
- Click Download CSV to export

### 4. Requirements 
- CSV Format Must contain: OverRideID,DCA,DCB,DCC,DCD
- Each JSON column must be an array of objects with "S" keys.

### 5. JSON Format 
- Each line must be: [{"S":"value1"},{"S":"value2"}]
- Invalid JSON lines are marked clearly.

Tips & Notes
- Very large CSVs (5k+ rows) may take longer to load — split them if needed.
- Search is case-insensitive and highlights exact substring matches.
- Hover inside cells to scroll long lists.
- Use Expand/Collapse for large comparisons.
- Theme toggle is helpful for long working sessions.
