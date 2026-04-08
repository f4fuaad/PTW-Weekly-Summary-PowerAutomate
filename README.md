# PTW-Weekly-Summary-PowerAutomate
Automated Weekly PTW Summary Report built using Power Automate —  pulls Active, Expiring, and Overdue/Failed permits from a  SharePoint PTW_Register list every Saturday and sends a branded  HTML email report to HSE management. Built as part of a full  Power Platform portfolio for an LNG mega-project environment.
# Weekly PTW Summary Report — Power Automate Portfolio Project

> Automated weekly Permit to Work (PTW) summary report built using 
> Power Automate — pulls Active, Expiring, and Overdue/Failed permits 
> from SharePoint and sends a branded HTML email every Saturday.

![Power Automate](https://img.shields.io/badge/Power%20Automate-0066FF?style=flat&logo=powerautomate&logoColor=white)
![SharePoint](https://img.shields.io/badge/SharePoint-0078D4?style=flat&logo=microsoftsharepoint&logoColor=white)
![Outlook](https://img.shields.io/badge/Outlook-0078D4?style=flat&logo=microsoftoutlook&logoColor=white)

---

## 🔍 Business Problem

HSE teams on large-scale industrial construction projects manage 
hundreds of Permits to Work simultaneously. Manually tracking 
active, expiring, and overdue permits is time-consuming and 
error-prone — critical permits can be missed, leading to safety 
risks and compliance failures.

---

## 💡 What Was Built

A fully automated scheduled Power Automate flow that runs every 
Saturday at 8:00 AM and sends a branded HTML summary email to 
the HSE team — with zero manual intervention required.

### Flow Steps

- **Recurrence Trigger** — Runs every Saturday 8:00 AM automatically
- **Get Active Permits** — Pulls all Active permits from SharePoint PTW_Register list
- **Filter Expiring Permits** — Identifies permits expiring within the next 7 days
- **Get Overdue/Failed Permits** — Pulls all Overdue and Failed permits
- **Create HTML Tables** — Formats each dataset into clean HTML tables
- **Compose Branded Email** — Builds a 3-section color-coded HTML report
- **Send Email** — Delivers the report via Office 365 Outlook

### Email Report Contains

- 📋 **Active Permits** — Total count + full permit table
- ⚠️ **Expiring This Week** — Permits expiring within 7 days (amber alert)
- 🔴 **Overdue / Failed** — Permits requiring immediate attention (red alert)

---

## 🗂️ SharePoint List — PTW_Register

| Column | Type | Purpose |
|---|---|---|
| Title | Single line | Permit number / ID |
| PermitType | Choice | Hot Work / Cold Work / Confined Space / Electrical |
| PermitStatus | Choice | Active / Expired / Closed / Pending / Overdue / Failed |
| IssuedDate | Date | When permit was issued |
| ExpiryDate | Date | When permit expires |
| Contractor | Single line | Contractor company name |
| Location | Single line | Work area / Zone |
| WorkDescription | Multi line | Description of work |
| IssuedBy | Person | HSE officer who issued |
| RequestedBy | Person | Person who requested |
| RiskLevel | Choice | Low / Medium / High |
| AlertSent | Yes/No | Email alert sent? |

---

## 🛠️ Tools & Stack

Power Automate | SharePoint Online | Office 365 Outlook

---

## 📐 Flow Architecture
```
Recurrence Trigger (Every Saturday 8:00 AM)
        ↓
Get Items — Active Permits (SharePoint PTW_Register)
        ↓
Create HTML Table 1 — Active Permits
        ↓
Filter Array — ExpiryDate ≤ Today + 7 days
        ↓
Create HTML Table 2 — Expiring This Week
        ↓
Get Items 2 — Overdue / Failed Permits (SharePoint PTW_Register)
        ↓
Create HTML Table 3 — Overdue / Failed
        ↓
Compose — Branded 3-Section HTML Email Body
        ↓
Send Email (Office 365 Outlook) → HSE Team
```
---

## 📸 Screenshots

### Flow Structure
![Flow Structure](Screen%20Shots%20of%20the%20Process/Workflow_SS.png)

### Email Output
![Email Output](Screen%20Shots%20of%20the%20Process/Email_SS.png)

---

## ⚠️ Data Note

All data shown is fully synthetic — no real company, project, 
or individual data is used. Generated for portfolio 
demonstration purposes only.

---

## 👤 Author

**Syed Mohammed Fuaad**
Power BI & Power Apps Developer | SHES Division | LNG Mega-Project, Qatar
3+ years building BI solutions and automation systems for industrial HSE teams.

[GitHub](https://github.com/f4fuaad) · [LinkedIn](https://www.linkedin.com/in/syed-fuaad) · [▶️ Equipment Inspection Tracker Demo](https://youtu.be/YI05PV3pmIM)
