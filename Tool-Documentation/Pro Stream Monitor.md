# **Pro Stream Monitor - User Guide**

### **Purpose**

The Pro Stream Monitor is a powerful browser-based tool designed for real-time monitoring of multiple live streams simultaneously. It allows operators to view, analyze, and manage streams from various sources (like playouts, encoders, or CDNs) — all in one dashboard — helping teams ensure uninterrupted broadcast quality.

Link: [Pro Stream Monitor](https://bhavesh-ses.github.io/URL-Monitoring-Tool/)

## **Overview**

The tool displays multiple video streams in a grid layout that can be customized to fit any screen or control-room display. It includes features such as:

- Automated health checks for stream availability.
- Alerts and audio notifications for stream failures.
- Screenshots and URL sharing for quick incident reporting.
- Real-time bandwidth tracking and performance insights.
- Page and audio rotation for large-scale monitoring.
- Light/Dark themes for different environments.

It’s lightweight, requires no installation or backend, and runs directly from a browser — making it highly portable and easy to use.

## **Why This Tool is So Useful**

In live broadcast or OTT operations, continuous monitoring of multiple feeds is critical. The **Pro Stream Monitor** simplifies that process with:

1.  **Single Dashboard View:** Watch multiple Playout/Encoder/Packager/Monitoring-Cache outputs or contribution feeds side by side, instead of switching between multiple players or tabs on console.  
2.  **Instant Problem Detection:** Automatically detects playback or network failures and visually highlights faulty streams.  
3.  **Operational Efficiency:** Helps engineers or operators quickly identify, isolate, and report stream issues — reducing response time during live events.  
4.  **Team Collaboration:** You can capture screenshots or share your entire dashboard layout via a single link, enabling fast communication between shifts or teams.  
5.  **Scalable Design:** Handles dozens of streams with responsive grid management, automatic rotation, and efficient bandwidth handling.  
6.  **Zero Setup:** Simply open the tool in a browser — no software installation, plugins, or backend configuration required.

## **Getting Started**

### **Step 1: Load Your Streams**

- Prepare a **CSV file** containing your streams in two columns:  
  **Column 1:** Stream Name  
  **Column 2:** Stream URL (HLS, DASH)  
- Click on **"CSV Upload"**, select your file, and the tool will automatically load all streams into the dashboard.

> _Tip:_ You can also share your loaded streams with others by clicking “Share” - this creates a URL containing your full layout and stream list.

### **Step 2: Adjust Your Layout**

Click the **Edit Layout** button on the top-right corner. In this menu, you can:

- Set **Rows** and **Columns** to match your display screen size.  
- Enable **Responsive Grid** to auto-fit boxes based on your screen width.  
- Choose **Auto-Rotate Pages** to automatically switch between groups of streams (useful when you have more streams than can fit on one screen).  
- Enable **Auto-Rotate Audio** to cycle audio between streams automatically.  
- Turn on **Playback Failure Check** to let the tool automatically detect and highlight failed streams.  
- Adjust **Staggered Loading** to avoid network congestion by loading streams in small batches.  
- Click **Save & Close** to apply.

> _Recommended:_ For large control-room screens, enable **Fit to View** and **Responsive Grid** for optimal viewing.

### **Step 3: Monitor the Streams**

Each stream appears in a Player Box with:

- The stream name at the top.  
- Controls for Quality, Screenshot, and Copy URL.  
- A status bar that turns red if an error occurs (e.g., stream down, buffering, or playback failure).

If any stream fails, you’ll see:

- A red overlay message on the affected box.  
- (Optional) An audio alarm sound — so you can instantly react.

### **Step 4: Use the Top Controls**

#### **Header Buttons**

| Button | Function |
|--------|----------|
| ⚙️ **Edit Layout** | Customize rows, columns, rotation, and behavior. |
| 🌗 **Theme** | Toggle between dark and light themes. |
| 🔔 / 🔕 **Alarm** | Turn stream failure audio alerts on/off. |
| 🔇 / 🔊 **Mute All** | Mute or unmute all streams at once. |
| ⏸️ / ▶️ **Pause / Play All** | Pause or resume all streams simultaneously. |
| ⛶ **Full Screen** | View all streams in full-screen mode. |
| 🔗 **Share** | Copy a shareable link of your current layout and streams. |

### **Step 5: Filter and Navigate**

#### **Search Box**

- Type any part of a stream name or URL to quickly filter visible streams.

#### **Pagination**

- Use Prev and Next buttons to move between pages if you have many streams.  
- Enable Auto Page Rotation to let the tool cycle through them automatically.

### **Step 6: Monitor Network Usage**

At the bottom-left, you’ll see the Network Usage Widget:

- **Speed (Mbps):** Real-time streaming bandwidth usage.  
- **Used (GB/MB):** Total data consumed since start or last reset.  
- **Since:** Start time of measurement.  
- **🧹 Reset:** Clears counters and restarts tracking.

This helps assess total network load from multiple active streams.

### **Step 7: Capture Screenshots**

- Each stream has a 📸 button to take a screenshot.  
- Screenshots are automatically timestamped with current UTC & channel name which is copied to clipboard automatically.
- Great for documenting playback issues or reporting stream health snapshots.

## **Additional Features**

### **Auto Rotation**

- **Page Rotation:** Automatically cycles through pages of streams at a set time interval.  
- **Audio Rotation:** Plays audio from one stream at a time and switches automatically after each interval.

> _Use Case:_ When you need to confirm that all feeds have audio presence periodically without manual switching.

### **Playback Failure Detection**

- The tool periodically checks whether each stream is reachable.  
- Failed streams are automatically highlighted and moved to the top-left for visibility.  
- If the stream recovers, it automatically reloads.

> _Benefit:_ You can instantly know which feed is down — no need to manually check each one.

### **Persistence & Customisation**

- All layout and behaviour settings are saved automatically in your browser (local storage).  
- Your preferences (rows, columns, rotation settings, etc.) are restored next time you open the tool.

## **Best Practices & Tips**

1.  **Before Monitoring:**

    - Ensure your internet connection is stable.  
    - Test your CSV list to confirm all URLs are correct and accessible.  
    - Interact with the page once (click or unmute) to allow alarm sounds — browsers block auto-sound until user interaction.

2.  **During Monitoring:**

    - Keep alarms enabled to catch any failures instantly.  
    - Use “Fit to View” for maximum visibility on big screens.  
    - Use “Pause All” during shift changes or troubleshooting to save bandwidth.

3.  **After Monitoring:**

    - Use the “Share” button to hand over the exact monitoring view to the next shift.  
    - Capture screenshots of problematic streams for documentation.

4.  **Performance Tip:**

    - For large setups, increase the stagger delay and batch size under Edit Layout to reduce CPU load during startup.

## **How It Helps Operations Teams**

| Challenge | How the Tool Solves It |
|-----------|------------------------|
| Monitoring many feeds at once | Multi-grid player layout with adjustable sizing |
| Detecting failed streams | Auto failure detection + alarm sound |
| Tracking network usage | Real-time Mbps and data consumption stats |
| Shift handovers & collaboration | Shareable URL + screenshots |
| Load balancing | Staggered loading for stable performance |
| Visual confirmation | Fit-to-view scaling and fullscreen mode |

## **In Summary**

**Pro Stream Monitor** turns your browser into a professional-grade live stream control wall — helping you **see, hear, and act instantly** on stream health.

It is:

- **Fast to set up** (runs in any modern browser)  
- **Lightweight and efficient** (client-side only)  
- **Highly customizable** (layout, alerts, rotation)  
- **Collaboration-ready** (share links, screenshots, reports)

Whether you’re monitoring a single Playout/Encoder/Packager/Monitoring-Cache feed or dozens of OTT streams during major events, this tool ensures that you always have **complete visibility** — making your operations smoother, faster, and more reliable.

---

## **Links**

- Pro Stream Monitoring Tool: [Pro Stream Monitor](https://bhavesh-ses.github.io/URL-Monitoring-Tool/)  
- Google sheet to create instant M2A/MK URLs with OAID: [M2A/MK Monitoring URL Creator Sheet](https://docs.google.com/spreadsheets/d/1O2lwykm8TecUezifPAs8yF3wHrBDSaDyNbMp7qaC__Y/edit?usp=sharing)

---

## **How to create the CSV file for uploading the URL’s on the Monitoring Tool**

1.  Open the [M2A/MK Monitoring URL Creator Sheet](https://docs.google.com/spreadsheets/d/1O2lwykm8TecUezifPAs8yF3wHrBDSaDyNbMp7qaC__Y/edit?usp=sharing) & Select the HE for which you need to create the URL for MK on Sheet 1 & M2A on Sheet 2.

    - **MK URL's Generator** - This sheet is for creating the MK HE URLs from OAID.  
    - **M2A URL's Generator** - This sheet is for creating the M2A HE URLs from OAID.  
    - **Channel Naming Formatter** - This sheet is for creating the Channels Name list quickly instead of manually typing.

2.  MK URL’s Generator for Unsuppressed Events:

    1.  MK URL’s Generator can create the URLs for both **DCG / DCH**. At the top you have a dropdown to select **DCG** or **DCH**, which will automatically change the formula to give the selected DC URLs.

        1.  **DCG** - `dcg-prda.uksouth-3`  
        2.  **DCH** - `dch-prda.westeurope-3`

    2.  In **Column A** enter the Custom channel name (helps identify/search on Monitoring tool).  
    3.  In **Column B** paste the **OAID** — Column C will auto-generate the HLS URL and Column D will auto-generate the DASH URL.  
    4.  Go to **Cell C56** (HLS) and **Cell D56** (DASH) — these contain the final formatted URLs.  
    5.  Copy the required column (HLS from C56 or DASH from D56) and paste into an empty `.csv` file.  
    6.  Upload the CSV into the Monitoring Tool.  
    7.  For **suppressed DCG events**, paste Custom Channel name in **A109**, OAID in **B109** — **C109** will generate the tokenized URL. Copy & paste into CSV → upload → playback starts instantly.

3.  M2A URL’s Generator:

    1.  M2A URL’s Generator supports DCs **DCA / DCB / DCC / DCD**. Use the dropdown to select the desired DC which updates formulas accordingly.

        1.  **DCA** - `m2a-dazn-preview-dca.m2amedia.services`  
        2.  **DCB** - `m2a-dazn-preview-dcb.m2amedia.services`  
        3.  **DCC** - `m2a-dazn-preview-dcc.m2amedia.services`  
        4.  **DCD** - `m2a-dazn-preview-dcd.m2amedia.services`

    2.  Column A → Custom channel name.  
    3.  Column B → OAID.  
    4.  Column C → HLS URL (auto).  
    5.  Column D → DASH URL (auto).  
    6.  Column E → SMOOTH URL (auto).  
    7.  Final formatted outputs are available at **C56 / D56 / E56** — copy required column and paste into CSV → upload.

4.  Channel Naming Formatter:

    1.  This creates formatted channel names from raw data. Select options like `DCA_HLS`, `DCB_HLS`, `DCH_HLS`.  
    2.  Paste **Override ID** in Column B and **Fixture Name** in Column C — Column D will auto-generate the custom name.  
    3.  Copy Column D as **Values** and paste where needed.

If you follow all the above steps then you can easily create the CSV file & create the customised Monitoring Tool layout.
