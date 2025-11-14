# Advanced NRQL Query Builder – User Guide

### **Overview**
The **Advanced NRQL Query Builder** is a web-based tool that allows users to build, save, load, and run structured NRQL-style queries against a JSON dataset.  
It supports table/column selection, filters, aggregations, grouping, and time ranges.  
Admins have extended management capabilities.

**Tool Link:** https://bhavesh-ses.github.io/Advanced-NRQL-Builder/

---

## Login & Signup

### **Login**
- Log in using email + password.

### **Signup**
Click **Sign Up** → provide:
- Name  
- Email  
- Password  

Authentication & roles are managed securely via **Firebase**.

---

##  User Roles

###  **Admin**
Admins have full privileges:
- Add / edit / delete *any* saved query  
- View all saved queries  
- (Future) Manage user roles  

###  **Normal User**
- Create, save, load, delete **their own queries only**
- Can only view/edit their own saved queries

---

## Table & Column Selection

1. Select a **table** from the dropdown  
   *(JavaScriptError, PageAction, MobileRequestError, etc.)*
2. Columns auto-populate for the selected table.
3. You can configure:
   - Columns to **display**
   - Aggregations (e.g., `count()`, `average(col)`)
   - Facet (group by) columns
   - Filter conditions (column + operator + value)

---

## Query Builder Options

### **1. Add Filter**
- Add multiple filters  
- Logical operators: **AND / OR**  
- Choose:
  - Column  
  - Operator (`=`, `!=`, `contains`, etc.)
  - Value  

### **2. Add Aggregation**
Common functions:
- `count()`
- `average(column)`
- `max(column)`
- `min(column)`

### **3. Facet Column**
- Group results by one or more columns

### **4. Time Range**
- Relative:
  - Last 30 mins
  - Last 1 hour
  - Last 24 hours  
- Absolute:
  - Custom start & end timestamps

### **5. Limit**
- Default: **100**
- User-configurable

### **6. Auto-Refresh**
- Enable live, recurring updates  
- Set refresh interval (e.g., **every 30s**)

---

## Save & Load Queries

### **Save Query**
Click **Save Query**, then enter:
- Query Name  
- Description  

Saved data includes:
- Table  
- Columns  
- Filters  
- Aggregations  
- Facets  
- Time range  
- Limit  
- Auto-refresh settings  
- Description  

Stored securely in **Firebase Firestore**.

---

### **Load Query**
Click **Load Query** → see list of saved queries.

Features:
- Dropdown with **Select2 search**
- Selecting a query loads:
  - Columns  
  - Filters  
  - Aggregations  
  - Time settings  
  - Limit  
  - Auto-refresh  
  - Description (read-only)

---

## Saved Query Management
- Users can delete **their own** saved queries
- Admins can delete **any** query
- Search + filter quickly using Select2 dropdown

---

## Notes & Tips
- **Auto-refresh bug workaround:** Toggle OFF → ON once if it doesn’t start automatically.
- Use meaningful **descriptions** so teammates understand each query.
- All stored data is protected via Firebase security rules.

---

## Example Use Case

### **Goal:**  
View **JavaScriptError** events for **iOS** users in the **last 30 minutes**, grouped by error message.

### Steps:
1. Select table: **JavaScriptError**
2. Select columns:  
   - `errorMessage`  
   - `appVersion`
3. Add filter:  
   - `platform = iOS`
4. Add aggregation:  
   - `count(*)`
5. Facet by:  
   - `errorMessage`
6. Time range:  
   - **Last 30 minutes**
7. Save query:  
   - **Name:** `iOS Errors`  
   - **Description:** `Error stats for iOS users`
8. Later → Load from dropdown to refresh/view again.
