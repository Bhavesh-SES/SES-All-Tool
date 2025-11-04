Advanced NRQL Query Builder – User Guide

**Overview:** Advanced NRQL Query Builder Tool is a web-based application that allows users to build, save, load, and run structured queries against a JSON-based dataset. It supports table and column selection, filter conditions, aggregation, grouping, and advanced query generation. Admins have extended capabilities to manage saved queries across users.

Link: [https://bhavesh-ses.github.io/Advanced-NRQL-Builder/](https://bhavesh-ses.github.io/Advanced-NRQL-Builder/)

**Login & Signup**

- Login: Users can log in using their email and password.
- Signup: New users can register by clicking the "Sign Up" button and filling in:
- Name
- Email
- Password
- Firebase authentication manages secure login and user roles.

**👤 User Roles**

**🔸 Admin**

**Admins have full access:**

- Can add/edit/delete saved queries for all users.
- Can manage user roles (if implemented in future).
- Has visibility of all saved queries.

**🔹 Normal User**

- Can create, save, load, and delete their own queries.
- Can only see and edit their own saved queries.

**Table & Column Selection**

- After login, select a table from the dropdown (e.g., JavaScriptError, PageAction, MobileRequestError, etc.).
- Upon selecting a table, available columns are auto-populated.
- You can choose:
- Which columns to display
- Which column(s) to use for aggregation (like count(), average(), etc.)
- Facet columns for breakdown
- Filter columns, operators (=, !=, contains, etc.), and filter values

**Query Builder Options**

**1\. Add Filter**

- Add multiple filters using logical conditions (AND, OR)
- Select column, operator, and input value

**2\. Add Aggregation**

- Use built-in functions like:
- count()
- average(column)
- max(column)
- min(column)

**3\. Facet Column**

- Select columns to group the results

**4\. Time Range**

- Choose relative time (e.g., Last 30 mins, Last 1 hour, Last 7 days, etc.)
- Or use custom time using absolute start and end

**5\. Limit**

- Set result limit (default: 100)

**6\. Auto Refresh**

- Enable auto-refresh for real-time monitoring
- Auto-refresh interval can be set (e.g., every 30s)

**Save & Load Queries**

**Save Query**

- Click “Save Query” after building your query
- You will be prompted to:
- Enter a Query Name
- Enter a Description (e.g., “Tracks mobile JS errors from Android users”)
- **Query is saved to Firebase with:**
- Table
- Columns
- Filters
- Aggregations
- Time range
- Limit
- Auto-refresh settings
- Description

**Load Query**

- Click “Load Query” to open saved queries
- You’ll see a dropdown list of your saved queries with:
- Query names
- Search box (enabled via Select2) to easily filter queries
- Upon selection, all previous configurations (filters, aggregations, etc.) are loaded
- The saved description is also shown in a read-only box

**Saved Query Management**

- You can delete any of your saved queries.
- Admins can delete any query.
- Filter and search easily via the Select2 dropdown search.

**Notes**

- Auto-Refresh Toggle Fix: Sometimes, the checkbox appears selected but doesn’t start refreshing. Just toggle it off and on once to activate.
- Description helps your team understand what each query does — use it well!
- All interactions are secure and stored on Firebase Firestore.

**Example Use Case**

Goal: View JavaScriptError data for iOS users in the last 30 minutes, grouped by error message.

**Steps:**

1.  Select table: JavaScriptError
2.  Select columns: errorMessage, appVersion
3.  Filter: platform = iOS
4.  Add aggregation: count(\*)
5.  Facet by: errorMessage
6.  Set Time: Last 30 minutes
7.  Save Query with name: iOS Errors, description: Error stats for iOS users
8.  Load query from the dropdown to view/refresh later.
