# **MK EAE – DCG & DCH – User Guide**

### **Purpose**

The **MK EAE – DCG & DCH Event Explorer** is an operational tool designed for monitoring, validating, and comparing MediaKind (MK) EAE event metadata across DCG and DCH regions. It is built specifically for Operations, L1/L2 Support, and Engineering teams to accelerate daily checks, troubleshooting, and shift handovers.

---

# **Tool Link**
https://bhavesh-ses.github.io/SES_EventViewer/

---

# **Operational Overview**

The tool retrieves event metadata from both MK regions and presents it in a clean, side-by-side structure.  
Users can quickly:

- Filter events by date range  
- Search across all event fields  
- Compare DCG and DCH event data  
- Expand any row to see raw metadata  
- Generate playback URLs for HLS/DASH  
- Create and share monitoring links  
- Export filtered results  
- Toggle views and control layout based on need  

It is designed to streamline pre-checks for daily events, resolve mismatches faster, and assist during live operations.

---

# **Key Features (Operational View)**

### **1. Date & Range Filtering**
Select **Start Date** and **End Date** to display all events within that timeframe.

### **2. Unified Search**
A single search box filters DCG and DCH tables simultaneously, helping identify events quickly based on:
- oaId  
- Description  
- Event type  
- HE information  
- Audio/Dolby details  
- Suppression mode  
- Any visible field  

### **3. Show/Hide DCH**
Use the Show DCH checkbox to toggle the secondary region.  
When hidden → DCG automatically expands to full width.  
When enabled → UI splits into two resizable panes.

### **4. Resizable Split View**
Drag the center divider to adjust the screen space between DCG and DCH depending on operational focus.

### **5. Raw JSON Viewer**
Every row includes a **RAW JSON** button that opens a formatted metadata popup, useful during RCA, escalations, and backend validation.

### **6. Detailed View Mode**
When enabled, clicking on a row opens a full detail popup showing the formatted metadata in a clean and readable view.

### **7. Playback URL Generator (HLS/DASH + Token)**
Select any event → build all required playback URLs (HLS, DASH, Tokenized variants).  
Helps teams validate suppressed events or playback behavior instantly.

### **8. Share Monitoring URL**
Creates a compact shareable link containing all selected playback details.  
Useful for:
- Escalations  
- Cross-team communication  
- Shift changeovers  
- Quick remote checks  

### **9. Export Data**
Exports filtered results for documentation, shift notes, or incident reviews.

### **10. Theme Toggle**
Switch between **Light** and **Dark** mode for better readability based on environment or personal preference.

### **11. Live UTC Clock**
Helps operators correlate event metadata timing with global schedules.

---

# **User Interface Layout**

### **Top Layer Controls**
- **Left:** Tool Name  
- **Center:** Search  
- **Mid-Right:**  
  - Share Monitoring URL  
  - Compare OAID  
  - Theme Toggle  
- **Right:** Live UTC Clock  

### **Second Layer Controls**
- Show DCH toggle  
- HLS / DASH / HLS Token / DASH Token selectors  
- Detailed View toggle  
- Refresh  
- Export  

Below all controls, region labels appear:
- **DCG Summary:** (Event Count, Token, etc.)  
- **DCH Summary:** shown only when enabled  

---

# **Operational Use Cases**

### **Pre-Event Checks**
Quickly verify:
- Event availability  
- HE parameters  
- Audio/Dolby setup  
- Suppression modes  
- Daily event lineup  

### **Live Operations**
- Validate discrepancies between DCG & DCH  
- Inspect raw JSON for issue diagnosis  
- Generate playback URLs instantly during incidents  

### **Shift Handover**
- Filter events of the day  
- Export key details  
- Share playable monitoring URLs with next shift  

### **Post-Incident / RCA**
- Compare region metadata  
- Retrieve raw records  
- Validate suppression/watermarking/CC attributes  

---

# **Summary**

The **MK EAE – DCG & DCH Event Explorer** provides operational teams with:

- Fast access to event metadata  
- Accurate DCG/DCH comparison  
- Rapid playback validation  
- Clean, readable data views  
- Efficient troubleshooting features  
- Quick sharing options for collaboration  
- A structured UI optimized for day-to-day workflows  

It significantly reduces the time required to analyze, compare, and operationalize MK EAE metadata.
