# **Livestream API Details Puller — User Guide**

## 1. Overview

**Livestream API Details Puller** fetches livestream metadata from configured outlets, shows it in a searchable table, helps you build preview/playback URLs across headends/protocols, compare the same stream across regions, run quick filters, export reports, and create shareable playback links so teammates can open the exact same layout.

**Tool Link:** https://bhavesh-ses.github.io/Livestream-API-Details-Puller/#/normal

---

## 2. Advantages

- **Faster troubleshooting** — inspect stream fields (OAID, DRM, start/end times, audio, overrides) in one place.  
- **Reproducible playback** — generate playback URLs and Share links so QA/eng can reproduce exactly what you see.  
- **Cross-region comparison** — instantly compare a single OAID across outlets and export a colored diff for audits.  
- **Filter & act** — find DRM / Dolby / geo-blocked streams across many outlets, select rows and create test URLs.  
- **Lightweight & shareable** — no heavy infra — runs from a static host + optional proxy for internal APIs.

---

## 3. Quick start

1. Open the tool.  
2. Choose an **Outlet** from the top dropdown (affects the *Normal* page).  
3. Click **Normal** to view streams for that outlet. Use the **Search** box (top) to filter.  
4. Select rows using the first-column checkboxes. Selected rows turn light-grey.  
5. Pick **Headends** and **Protocols** above the table.  
6. Click **Create URLs & Export** to download CSV, or **Share Playback URL** to copy a link that recreates this layout in the playback tool.

---

## 4. UI walkthrough

### Header
- **Search** — global, debounced; matches table text and raw JSON; matches are highlighted.  
- **Outlet dropdown** — selects which outlet the Normal page shows.  
- **Reload** — clears cache and refetches.  
- **Extract** — XLSX export of the whole current outlet’s table.  
- **Details (toggle)** — enable to view Raw JSON modal when clicking a row.  
- **Theme (toggle)** — switch light/dark UI.

### Left panel
- Outlet checkboxes (one per region). Select multiple outlets for **Compare** or **Filters**.  
- **All** button toggles selecting all outlets.

### Pages
- **Normal Page** - flat table for the selected outlet (select rows, create/export/share URLs).  
  - First column checkboxes: select rows; first column remains visible when scrolling horizontally.  
  - Header checkbox selects/unselects all visible rows.  
  - Headends & Protocols area: choose where and how to build preview URLs.

- **Compare Page** - enter an OAID and compare it across selected outlets (left panel).  
  - Shows side-by-side JSON + a diff table (match/diff).  
  - **Export Compare** -> XLSX with coloured cells and JSON sheets.

- **Filters Page** - run pre-defined filters (DRM / Dolby / Geoblocks) across selected outlets.  
  - Results appear as per-outlet tabs; operate on the active tab only.

---

## 5. Step-by-step workflows (with quick checklists)

### Workflow A — Quick playback URLs for QA (Normal page)
1. Open **Normal** and choose Outlet at the top dropdown.  
2. Use **Search** to narrow streams (optional).  
3. Check the rows you need (first column).  
4. Choose Headend(s) and Protocol(s).  
5. Click **Create URLs & Export** → download CSV with labelled URLs.  
   OR click **Share Playback URL** → copy link & send to colleague.

**Checklist:** selected rows change to light-grey; first column sticky; CSV downloaded or share link copied.

---

### Workflow B — Compare OAID across regions (Compare page)
1. Select multiple outlets on the left (order matters — first becomes reference).  
2. Go to **Compare**. Type OAID and click **Search & Compare**.  
3. Wait for the fetch progress loader to complete.  
4. Review side-by-side JSON and colored diffs.  
5. Click **Export Compare** to get the styled XLSX report.

**Outcome:** clear view of where metadata diverges (useful after ingest or deployments).

---

### Workflow C — Find problem groups & export URLs (Filters)
1. Select outlets on left.  
2. Open **Filters**. Choose a filter (DRM / Dolby / Geoblocks) and **Run Filter**.  
3. Click the outlet tab you want to inspect.  
4. Select rows (or leave none selected to use all visible).  
5. Choose headends/protocols and click **Create URLs & Export** or **Share Playback URL**.

**Use case:** quickly gather test URLs for streams with a specific issue.

---

## 6. Share Playback URL — what it encodes & how to use it

- Encodes the selected streams (name + URL lines) in **Base64** plus layout params (rows, cols, refresh, etc.).  
- Preserves selection order — first selected becomes first player.  
- Use to send a single link to QA or engineering so they can open the same layout without manual setup.

---

## 7. Export behavior & formats

- **Create URLs & Export (CSV)** — label + URL pairs, one per headend/protocol combination per selected stream.  
- **Extract (XLSX)** — full table for the selected outlet (good for archival).  
- **Export Compare (XLSX)** — styled workbook:
  - Header: Cambria, 16pt, bold, grey background, centered, bordered.  
  - Data: Calibri, 11pt, centered. Light green = match; light red = diff; light yellow = not found; full borders.  
  - Includes per-outlet JSON sheets with borders.

---

## 8. Operation use cases (real world examples)

**Use case 1 — Nightly ingest verification**  
After nightly ingest, run Filters → DRM to confirm flagged streams. Export and send CSV to ingest team. Use Share URL to open a playback layout to eyeball failing streams.

**Use case 2 — Regional inconsistency discovery**  
Ops detects playback issues in Italy. Use Compare with OAID across DACH, Italy, USA to find metadata mismatches (e.g., missing audioConfig). Export Compare XLSX for postmortem.

**Use case 3 — QA playback session**  
QA wants to test 6 players in a 2×3 grid. Select 6 streams (Normal), choose headend HLS, create Share URL with `rows=2&cols=3`, send link to QA.

**Use case 4 — On-call incident**  
On-call receives alert for DRM mismatch. Use Filters (DRM) and Compare to narrow affected outlets, export URLs for immediate playback checks, and share the playback URL with the video team.

---

## 9. Troubleshooting & quick fixes

- **403 / no data:** upstream API is IP-restricted or CORS-blocked.  
  - If using GitHub Pages static host, set up a proxy inside office network or use a server reachable from allowed IPs.  
  - For local testing use the local proxy (`localhost:8000`) and run it via `pm2`/`systemd`.

- **Share link too long / cut by messenger:** shorten via server-side store (recommended for many streams).  
- **Export color not seen:** open XLSX in Excel (not a plain text viewer); ensure the viewer supports cell fills.  
- **Selection not persisting:** selection is global — confirm you are using the same browser tab/session and not clearing selections between views.

---

## 10. Quick reference / cheat sheet (copy for desk)

### Normal page
- Search → filter  
- Select rows → light-grey  
- Headends & Protocols → pick  
- Create URLs & Export → CSV  
- Share Playback URL → copies link

### Compare
- Select outlets (left) → first = reference  
- Enter OAID → Search & Compare  
- Export Compare → XLSX (colored diffs + JSON)

### Filters
- Select outlets → Choose filter → Run Filter  
- Switch outlet tabs → select rows → Create URLs / Share
