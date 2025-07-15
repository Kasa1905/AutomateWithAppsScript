# Code for Comparing Multiple Registrations

This folder contains Google Apps Script utilities for analyzing and comparing event registration data across multiple Google Sheets. These scripts help event organizers quickly identify common participants, overlapping registrations, and other useful insights from their registration spreadsheets.

---

## Scripts Included

### 1. `eventRegistrationComparator.js`
- **Purpose:**  
  Compares email registrations across multiple event sheets and finds the number of common participants between each pair of events.
- **Output:**  
  Creates/updates a sheet named `EventPairs` with a table showing each event pair and the count of common registrations.

### 2. `eventRegistrationComparator(mail ids as output).js`
- **Purpose:**  
  Compares email registrations across multiple event sheets and lists the actual email addresses common to each pair of events.
- **Output:**  
  Creates/updates a sheet named `EventPairs` with a table showing each event pair and the list of common email addresses.

### 3. `Finding multiple registration from same mail id.js`
- **Purpose:**  
  Identifies email addresses that have registered for more than one event.
- **Output:**  
  Creates/updates a sheet named `MultipleRegistrations` with a table listing each email and the events they registered for.

---

## How to Use

1. **Copy the desired script(s) into the Apps Script editor** attached to your Google Spreadsheet containing the event registration sheets.
2. **Edit the `sheetNames` array** at the top of each script to include the exact names of your event sheets:
   ```javascript
   var sheetNames = ["Event1", "Event2", "Event3"];
   ```
3. **Run the main function** in each script from the Apps Script editor:
   - For comparators: `compareEventRegistrations()`
   - For multiple registration finder: `extractMultipleRegistrations()`
4. **Check the output sheets** (`EventPairs` or `MultipleRegistrations`) in your spreadsheet for results.

---

## Notes

- All scripts assume that email addresses are in **column B** of each event sheet, with the first row as a header.
- If the output sheet (`EventPairs` or `MultipleRegistrations`) does not exist, the script will create it automatically.
- Existing data in the output sheet will be cleared each time the script runs.

---

## Requirements

- Google Sheets with event registration data
- Google Apps Script access
- Email addresses in column B of each event sheet
- First row as header in each sheet

---

## Example Output

### EventPairs Sheet (Count Version)
| Event 1 | Event 2 | Common Participants |
|---------|---------|-------------------|
| Workshop A | Workshop B | 15 |
| Workshop A | Workshop C | 8 |
| Workshop B | Workshop C | 12 |

### EventPairs Sheet (Email List Version)
| Event 1 | Event 2 | Common Email Addresses |
|---------|---------|----------------------|
| Workshop A | Workshop B | user1@example.com, user2@example.com, ... |

### MultipleRegistrations Sheet
| Email Address | Events Registered |
|---------------|------------------|
| user1@example.com | Workshop A, Workshop B, Workshop C |
| user2@example.com | Workshop A, Workshop B |
