 ## ARS Atlas Roadways – LR Entry & Print System

**Client Live Project Documentation**
Web-based logistics LR (Lorry Receipt) entry, billing classification, and pre-printed form alignment printing system.

---

##  1. Project Overview

This project is a **transport/logistics office automation system** designed for a road transport company to replace handwritten LR (Lorry Receipt) books while still using their existing pre-printed stationery.

The system allows a booking clerk to:

* Enter consignor & consignee details
* Record parcel/article information
* Select billing type (**PAID / TO-PAY / TBB / MEMO**)
* Automatically place values in exact positions
* Print directly onto a pre-printed physical LR slip (**210mm × 165mm**)

Instead of printing a full page, the software prints **only the required text fields** exactly where blanks exist on the company’s already printed LR forms.

>  This is NOT a normal invoice generator.
> It is a **precise print-alignment overlay system.**

---

##  2. Core Problem This Project Solves

Many transport companies in India still use:

* Pre-printed LR books
* Rubber stamps
* Handwritten entries

### Problems Faced by Client

* Writing errors
* Manual miscalculations
* Slow booking counter operations
* Duplicate LR copies difficult to maintain
* Staff handwriting issues
* No searchable records

### Solution

This software digitizes LR entry **without changing their existing paper system.**

 Physical paper remains same
 Only handwriting is replaced with computer-printed text

---

##  3. Real Office Workflow

1. Booking clerk opens system dashboard
2. Selects LR type (**PAID / TO-PAY / TBB / MEMO**)
3. Fills booking form
4. Inserts pre-printed LR slip into printer
5. Clicks **PRINT**
6. System prints values exactly inside blank boxes

 Result: Perfect printed LR within 5 seconds.

---

##  4. Technology Stack

| Component     | Technology                        |
| ------------- | --------------------------------- |
| Frontend      | HTML5 + CSS3 + Vanilla JavaScript |
| Layout System | Absolute positioning print layout |
| Print Engine  | html2pdf.js                       |
| UI Design     | Custom CSS (No Framework)         |
| Data Storage  | MySQL (Production – Not Included) |
| Output        | Printer-aligned overlay printing  |

> Important: Public repository does NOT include database schema or credentials.

---

##  Database (Confidential)

Production system uses **MySQL** for storing:

* LR entries
* Booking records
* Reports

For security reasons, the following are NOT included:

* Database schema
* Table structure
* Connection strings
* Credentials

This repository contains only the **application interface and printing modules**.

---

##  5. Folder Structure

```
final atlas done/
│
├── index.html
├── PAID.html
├── TOPAY.html
├── TBB.html
├── memo.html
│
├── images/
│   └── a_r_s.jpeg
│
├── print-templates/
│   ├── PAID.png
│   ├── TOPAY.png
│   ├── TBB.png
│   ├── memo.jpeg
│   └── QR.jpeg
```

---

##  6. Dashboard (index.html)

The dashboard acts as the system navigation hub.

### Features

* Company identity header
* Logo display
* Office details
* Sidebar navigation

### Available Modules

* PAID
* TO PAY
* TBB
* MEMO

Designed for **quick selection during booking rush hours.**

---

##  7. LR Entry Modules

Each module represents a real logistics billing category.

---

### 7.1 PAID (PAID.html)

Used when sender pays full freight at booking time.

**Clerk Enters:**

* Consignor
* Consignee
* From City
* Destination
* Packages
* Article description
* Weight
* Freight
* Charges

System maps values to fixed coordinates and prints on **PAID LR slip**.

---

### 7.2 TO-PAY (TOPAY.html)

Used when receiver pays freight at destination branch.

* Freight not collected at booking
* Marked payable at delivery branch
* Slip marking differs from PAID

---

### 7.3 TBB – To Be Billed (TBB.html)

Used for corporate customers with monthly billing accounts.

* No immediate payment
* Freight added to ledger
* Billed month-end

---

### 7.4 MEMO (memo.html)

Internal transfer slip.

Used for:

* Branch stock movement
* Office-to-office parcel transfer
* Internal tracking

No payment involved.

---

##  8. Print Alignment System (Most Critical)

### Paper Size

**210mm × 165mm**
(Custom transport LR paper – NOT A4)

### Printing Method

* Absolute CSS positioning
* Fixed pixel mapping
* Printer scaling disabled

### Required Printer Settings

* Paper size: Custom 210mm × 165mm
* Scaling: 100%
* Margins: None
* Fit to page: OFF
* Center: OFF

 If any setting changes → text shifts from boxes.

---

##  9. Template & QR Files

Located inside `print-templates/`

Used for:

* Developer alignment reference
* Coordinate calculation
* Physical paper matching

Not printed in final output.

---

##  10. Printing Mechanism

Library Used:

```
html2pdf.js
```

Process:

1. Form values captured
2. Injected into print layout container
3. Converted to PDF canvas
4. Browser print command executed
5. Text printed over physical slip

---

##  11. How to Run Locally

### Simple Method

Just open:

```
index.html
```

Works completely offline.

---

##  12. Deployment (Office Setup)

Recommended:

* Dedicated booking PC
* Laser printer
* Custom paper tray loaded
* Microsoft Edge browser
* Zoom level: 100%

 Do NOT change browser zoom or Windows display scaling.

---

##  13. Customization Guide

### Change Company Details

Edit:

```
index.html → header section
```

### Adjust Print Alignment

Edit CSS absolute positions inside LR page.

Example:

```css
.top-left {
  left: 120px;
  top: 84px;
}
```

Move pixel values until text aligns perfectly.

---

##  14. Known Limitations

* No database details included
* No LR search
* No user authentication
* Fixed printer dependency
* Screen resolution sensitive
* Designed as counter tool (Not ERP)

---

##  15. Recommended Future Improvements

* LR number auto generation
* Daily booking report
* GST billing export
* Branch networking
* Thermal printer support
* PDF archival
* User authentication

---

##  16. Security Notes

* Runs locally
* No internet exposure
* No external data transmission
* Safe for internal office network

---

##  17. Developer Notes

This project required real-world calibration.
Each field was manually aligned using physical test prints.

This type of system is known as:

> **Print Overlay Alignment Software**

Common in Indian transport, courier, and warehouse industries.

---

##  18. Credits

**Client:** ARS Atlas Roadways
**Project Type:** Live Operational Logistics Software
**Purpose:** LR Entry Automation & Pre-Printed Slip Printing

---

##  19. License

Private Client Project.
Not intended for public commercial redistribution without permission.

---

#  End of Documentation
