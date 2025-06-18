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

## About the Repository

This repository contains multiple folders for automating and analyzing event registration workflows using Google Apps Script, including:

- **Complete ticket automation**
- **Mail sending from registration entries to reminders**
- **Code for Comparing multiple registrations** (**this folder**)
- **Few Other Codes**

Each folder includes its own README and scripts for specific automation tasks.

---

## License

These scripts are provided as-is for internal automation and analysis. Please review and adapt them as needed for your use case.