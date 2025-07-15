# Ticket Automation with QR Code Generation

This project automates the process of generating QR codes for event tickets and sending them via email using Google Apps Script. It is designed for use with Google Sheets and Google Drive.

---

## Overview

The solution consists of two main scripts:

1. **QRcode_genration.js**  
   Generates QR codes for each ticket based on a unique Team ID and saves them to a specified Google Drive folder.

2. **Sending_ticketc_with_QR_placing.js**  
   Sends personalized emails to ticket holders with their ticket details and the corresponding QR code attached.

---

## 1. QRcode_genration.js

**Purpose:**  
Reads ticket data from a Google Sheet, generates a QR code for each ticket using the Team ID, and saves the QR code image to a Google Drive folder.

**How it works:**
- Reads all rows from the specified Google Sheet.
- For each row, generates a QR code using the [QuickChart API](https://quickchart.io/qr).
- Saves the QR code image as `{TeamID}.png` in the specified Google Drive folder.
- If a QR code image already exists for a Team ID, it replaces the old image.

**Setup:**
- Set your Google Sheet ID, sheet name, and Google Drive folder ID at the top of the script.

---

## 2. Sending_ticketc_with_QR_placing.js

**Purpose:**  
Sends an email to each ticket holder with their personalized ticket and QR code attached.

**How it works:**
- Reads ticket data from the Google Sheet.
- For each unsent ticket, finds the corresponding QR code image in the Drive folder.
- Loads an HTML email template (`ticket.html`), replaces placeholders with ticket data, and embeds the QR code image.
- Sends the email with the QR code attached.
- Marks the ticket as "Sent" in the sheet to avoid duplicate emails.
- Sends a summary report to the admin email after all emails are sent.

**Setup:**
- Set your Google Sheet ID, sheet name, Google Drive folder ID, and admin email at the top of the script.
- Ensure you have an HTML file named `ticket.html` in your Apps Script project with the required placeholders: `{Name}`, `{Time}`, `{Location}`, `{id}`, `{qr_image}`.

---

## Prerequisites

- A Google Sheet with ticket data (columns: Email, Name, ID, Location, Time, etc.).
- A Google Drive folder to store QR code images.
- Google Apps Script project linked to your Google account.

---

## Usage

1. **Generate QR Codes:**
   - Run the `generateAndSaveQRCodes` function in `QRcode_genration.js`.

2. **Send Emails:**
   - Run the `sendEmailsWithQR` function in `Sending_ticketc_with_QR_placing.js`.

---

## Notes

- Update all placeholder values (`YOUR SHEET ID`, `SHEET NAME`, `FOLDER ID`, `ADMIN MAIL ID`) with your actual data.
- The QR code images are made accessible via a public link for embedding in emails.
- The script marks tickets as "Sent" to prevent duplicate emails.

---

## License

This project is for educational and internal event automation use.