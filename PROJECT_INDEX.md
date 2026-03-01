# Insurance Claims Review - Project Index & Summary

## Project Overview

**Purpose:** Build an orchestrated Claude Code workflow system where Emma (independent contractor for Loss Solutions Group, LLC) can provide zip files containing insurance claim research documentation, and Claude subagents can produce high-quality finalized reports and invoice summaries consistent with the required style guidelines.

**Author of reports:** Tanner Beuret, Technical Consultant, Loss Solutions Group, LLC
**Contractor:** Emma (uses Claude to assist with report writing)
**Company:** Loss Solutions Group, LLC (LSG) - equipment loss consulting for insurance companies

---

## Previous Conversation Summary (Session 1 - March 1, 2026, ~4:55 AM)

### What Was Accomplished
1. Emma explained the project: She works as an independent contractor reviewing insurance claims (desk jobs - no onsite visits). She receives claim details from adjusters, investigates by calling claimants/vendors/contractors, documents everything, and produces a final report with cost assessment.
2. Claude read all 3 email PDFs from Tanner Beuret with instructions.
3. Claude read and extracted the template document (`3_1_26 help write up reports template.docx`).
4. Claude did a deep-dive analysis of the **Main Street Tacos LLC** bundle (complete end-to-end: File Notes → Spreadsheet → Invoice Summary → Final Report PDF).
5. Three background subagents were launched to analyze: (a) first 8 bundles, (b) second 8 bundles, (c) random claims reference data. Two of three hit rate/context limits before completing.
6. Session ended at context limit before any files were committed to git.

### What Was NOT Completed
- No git commits were made (repo was initialized but empty)
- No system documentation was written for subagent orchestration
- The 6 pending claims from Email #3 were not started
- No report-generation pipeline was built
- The notes.zip from "random claims" is corrupt and may need to be re-obtained from Tanner

---

## Directory Structure & File Index

### Root Level Files

| File | Purpose |
|------|---------|
| `3_1_26 help write up reports template.docx` | **THE BIBLE** - Master template/style guide for all reports. Contains exact section structure, language patterns, and special-case rules. |
| `#1 most recent claims and the word doc to copy off of - *.pdf` | Email #1 from Tanner: Instructions about the template, keep it simple/not AI-sounding, be vague where appropriate, also produce Invoice Summary, round minutes up to nearest 15-min increment. |
| `#1 most recent claims and the word doc to copy off of.eml` | Raw email file (same as above PDF but as .eml) |
| `#2 random claims (lots) - *.pdf` | Email #2 from Tanner: Just zip attachments (invoice summaries, notes.zip [CORRUPT], reports, spreadsheets) for historical reference. |
| `#3 list of the six (6) claims i need reports and invoice summaries for - *.pdf` | Email #3 from Tanner: Lists 6 specific claims needing reports with per-claim special instructions. |
| `.gitignore` | Git ignore rules |
| `PROJECT_INDEX.md` | This file |

### `Previous_Conversations/`

| File | Purpose |
|------|---------|
| `Terminal Saved Output_4.55am` | Full terminal log of the first Claude Code session. Contains all exploration and analysis work done. |

### `eight report bundles/` (First 8 Complete Sample Bundles)

Each bundle is a subdirectory named `{MatterNumber} - {InsuredName}` containing a complete claim with all working files AND the finalized report PDF.

| Bundle | Key Details |
|--------|-------------|
| `426600.4162-00 - Spare Time Inc. (#1) - 85-00893419` | Has: Assignment & Budget Approval, Info-Estimates/notes, MIW, Photos, Report Format, Final Report 2-10-26, File Notes, Spreadsheet, Invoice Summary, PRICE CHECK subfolder |
| `426600.4163-00 - Spare Time Inc. (#2) - 85-00900748` | Second claim for same insured (different claim#). Has: photos of Backflow preventer subfolder, PRICE CHECK subfolder |
| `427800.16574-00 - Main Street Tacos LLC` | **DEEPLY ANALYZED IN SESSION 1.** Fire claim - vent hood + walk-in cooler. Includes vendor fraud investigation (Ice Berg invoice was fake). Has: docs from vendor subfolder, PRICE CHECK subfolder |
| `427800.16599-00 - Richard Hurtado DBA OG Birrieria` | 11 photos, docs from vendor subfolder, All photos compiled in docx, PRICE CHECK subfolder |
| `724300.0059-00 - Usie Real Estate Holdings LLC` | Standard bundle. Has: price check subfolder |
| `787200.11940-00 - BOURBON GRILL & MORE, LLC` | Has: docs from adjuster subfolder, docs from EF vendor subfolder, 4 photos, Photos from insured.docx, Report Format, PRICE CHECK subfolder |
| `787200.12584-00 - Bay Crane Service #1 (CDU)` | CDU (Condensing Unit) claim. Has: multiple Info PDFs, email correspondence, forklift incident docs, Texas Air Systems shipping damage doc, from emm subfolder, price check subfolder |
| `787200.12739-00 - Becnel Rental Tools` | Has: Info as both PDF and XLSX, Report Format, PRICE CHECK subfolder |

#### Standard Files in Each Bundle
Every bundle typically contains these file types:
- **Assignment PDF** (or Assignment & Budget Approval) - The initial assignment from the insurance adjuster
- **MIW.pdf** (Master Information Worksheet) - Key claim metadata
- **File Notes Worksheet (.docx)** - Tanner's raw call notes, timestamps, and investigation diary
- **SPREADSHEET (.xlsx)** - Cost analysis with CLAIM PRESENTED vs LSG RESEARCHED RCV columns, depreciation calculations
- **Invoice Summary (.xlsx)** - Billing summary with hours by activity category at $175/hr
- **Report Format (.docx)** - The partially-filled report template for this specific claim
- **Final Report PDF** (dated) - The finished, signed-off report sent to the client
- **Info PDFs** - Vendor proposals, invoices, estimates, emails from parties
- **Photos** - Damage photos (JPG, PNG, BMP, or compiled into a DOCX)
- **PRICE CHECK subfolder** - Screenshots of online price research (supplier websites, product listings)

### `another set of eight report bundles/` (Second 8 Complete Sample Bundles)

| Bundle | Key Details |
|--------|-------------|
| `787200.12767-00 - I 69 INVESTMENTS LLC` | Has: 8 photos (Data Plate, Impact 1-4, Overview, Pump 1-3), ECT QUOTE PRESENTED.pdf, All photos.docx, price check subfolder |
| `787200.12787-00 - CJ Shaughnessy Crane Svc Inc.` | Has: Incident Report, 3 PNG photos, Trane email (voiding warranty), more docs from adj subfolder, price check subfolder |
| `787200.12801-00 - LIQUID 8 TECHNOLOGY, INC.` | Has: Proposal #25286, 3 photos, Report Format, more photos subfolder, price check subfolder |
| `787200.12811-00 - SYRACUSE MATTRESS & FURNITURE` | Has: 2 Assignments, Info-Falso.pdf, Isaac AC Replacement Quote, 1 photo, Report Format, PRICE CHECK subfolder with price check docx |
| `787200.12831-00 - MOON EXPRESS INC` | Transit/shipping damage claim. Has: BOL (Bill of Lading), trucking rate confirmation, claim form, multiple screenshots, Total updated costs.docx, old quotes, price check subfolder |
| `787200.12859-00 - Denver Meyers` | Has: 3ton split 15 seer Ruud info, mandatory PDF, 4 photos, Report Format, All photos docx, price check subfolder |
| `787200.12863-00 - Robin Vergato` | Has: Invoice27885 + breakdown docx, 6 photos + 1 BMP, Report Format, All photos docx, price check subfolder with 13 screenshots |
| `787200.12867-00 - Interstate Gourmet Coffee` | Has: 2 Assignments, Info & Photos combined PDF, light pole photos, Report Format, All photos docx, price check subfolder |

### `random claims (lots)/` (Historical Reference Data - Partial)

From Email #2. Contains finalized outputs from ~16 historical claims but **NOT the working notes** (notes.zip was corrupt).

| Subfolder | Contents |
|-----------|----------|
| `reports/` | 16 finalized report PDFs (completed reports sent to clients). Claims include: ALSON-THORNTON, HAW CREEK PRESSURE WASHING, Green Carriers Express, Barbour County Commission, VANCE THOMPSON VISION CLINIC, MPW Surfacing Holdings, FCS Building Association, Kandie White, Castle Hill Sewer Association, INTERNATIONAL LINING TECHNOLOGY, MODULE X SOLUTIONS, Mandelbaum Third Generation, VALRICO PIZZA, John Kwasneski, Sakura Japanese Steakhouse, Vince Gentiluomo |
| `invoice summary/` | 8 Invoice Summary XLSX files for subset of above claims |
| `spreadsheets/` | 8 cost analysis XLSX spreadsheets for subset of above claims |
| `*.zip` | Original zip archives (reports.zip, invoice summary.zip, spreadsheets.zip, notes.zip [CORRUPT]) |

---

## Report Template Structure (from `3_1_26 help write up reports template.docx`)

### Required Report Sections (in order):
1. **Header** - LSG letterhead, date, adjuster name/address, RE block (Insured, Claim#, LSG Matter#, Date of Loss)
2. **Salutation** - "Dear Ms./Mr. [Adjuster],"
3. **Opening** - "Thank you for choosing Loss Solutions Group as your equipment loss consultant..."
4. **Assignment** - Who contacted LSG, scope of assignment (assess cause of loss, extent of damage, repair costs, salvage value), what equipment, what event, what date
5. **Findings and Analysis** - Detailed narrative of all contacts made (insured, vendors, third parties). Each contact gets its own paragraph with name, company, phone, and what they reported. Ends with "A total amount of $X was presented."
6. **Scope of Damage** - Brief restatement of what was damaged and when
7. **Age & Condition** - Age of equipment and condition at time of loss
8. **Cause of Loss** - What caused the damage (fire, vandalism, wind, transit, etc.) with verification method
9. **Reparability** - Whether repair or replacement is warranted
10. **Cost Analysis** - Per-vendor breakdown with proposal/invoice details. For each vendor: total amount, what's included, labor review, "fair and reasonable" determination
11. **RCV** (Replacement Cost Value) - Total fair and reasonable amount with reference to attached spreadsheet
12. **ACV** (Actual Cash Value) - Depreciated value based on linear age depreciation of materials only, with estimated life expectancy
13. **Salvage** - Either "little to no salvage value" (standard) or "refer to internal salvage department" (Hartford claims)
14. **Summary** - Numbered list: (1) What was damaged + total presented, (2) Age/condition, (3) RCV amount, (4) ACV amount, (5) Salvage statement
15. **Closing** - Contact info for Tanner Beuret (ext 755) and Team Leader Nick Ramos (ext 724)
16. **Signature** - "Best regards, Tanner Beuret, Technical Consultant, Loss Solutions Group, LLC"

### Critical Style Rules:
- **"Reportedly"** - MUST be used when describing claims/events (we are not making the claim)
- **Simple language** - Do NOT sound AI-generated or overly professional. Keep it fast and simple.
- **Be vague on specifics** - e.g., "various sizes of pipe" not "1-inch, 1.5-inch, and 2-inch pipe"
- **Hartford claims** get different salvage language: "Please refer to your internal salvage department to assess the salvage potential"
- **Non-Hartford claims** get: "Loss Solutions Group submits that there is little to no salvage value associated with this claimed event"
- **New/unused equipment** - Skip ACV analysis entirely: "Loss Solutions Group has not completed an actual cash value (ACV) analysis for this claimed event, as the equipment was in new and unused condition"
- **Lump sum costs** - When a vendor gives a single price, work with them to break it down. Note: "This price was given to us in a lump sum cost. With help from the vendor we were able to break this cost down as follows."
- **Multiple vendors** - Each vendor gets their own Cost Analysis subsection with bold header: "VENDOR NAME (PHONE) PROPOSAL/INVOICE # NUMBER"
- **Further research** - When third-party vendors are contacted for price validation, document in the Findings section

### Spreadsheet Structure:
- **Header**: Insured name, LSG Matter#, Claim#, Date of Loss, Cause of Loss
- **Per-vendor table** with columns: REF#, ITEM, CLAIM PRESENTED (QTY/UNIT COST/TOTAL), LSG RESEARCHED RCV (QTY/UNIT COST/TOTAL), AGE(YEARS), USEFUL LIFE(YEARS), ACV(MAX DEPRECIATION 75%), DEPRECIATION, CONDITION, NOTES
- **Depreciation rules**:
  - Materials: Linear depreciation = Age/Useful Life, capped at 75% max
  - Labor: N/A (not depreciated)
  - Permits: N/A (not depreciated)
  - Disposal: N/A (not depreciated)
  - Condition typically "AVERAGE" for used equipment, "N/A" for labor/permits/disposal
- **Summary section**: SUB-TOTAL, SALES TAX, TOTAL for each vendor, then TOTAL PRESENTED, TOTAL RESEARCHED RCV, TOTAL ACV, TOTAL DEPRECIATION

### Invoice Summary Structure:
- **Columns**: Date, Hours, Matter Number, Matter Name, Activity, Pay Rate, Ext Rate (Earnings), Consultant
- **Activity categories**: File Review & Client Contact, Insured, Vendors, Research & Technical Analysis, Report & Spreadsheet
- **Pay rate**: $175/hr
- **Hours**: Rounded UP to nearest 0.25hr (15-minute) increment
- **Time estimation**: If raw notes show 20 minutes, round up to 30 minutes (nearest 15-min increment above actual)
- **Footer**: Subtotals, Mileage (usually 0 for desk jobs), Total, Adjuster info, Insured info, Claim#, Budget

---

## Special Case Patterns Identified

### From Email #3 - Six Pending Claims with Special Instructions:

1. **BAY CRANE SERVICE (radiator)** - Edge case: No cost breakdown available from vendor/insured for transformer repair. Calculate repair cost proportionate to original unit cost. New unit = manufacturer voids warranty, so 30% repair cost is reasonable. Audio file "Bay Crain with Nick" has manager explaining exact verbiage.

2. **WESTSIDE MECHANICAL GROUP** - Standard case (no special instructions noted)

3. **PASTEUR PLAZA SURGERY CENTER** - Standard case (no special instructions noted)

4. **GJC BROTHERS INC.** - Standard case (no special instructions noted)

5. **PRECISION WIRE FORMS, INC.** - Must state: "we received a verbal quote from Welding Mart Mr. Jeremiah"

6. **AL & VAL, INC., DBA CHARLIE'S DINER** - Must look up electrical/fire codes to cite that the work performed was necessary for re-opening

### From Sample Analysis - Variation Patterns:

- **Vendor fraud/legitimacy issues** (Main Street Tacos): When a vendor's invoice can't be verified, document the full investigation trail in Findings
- **Multiple proposals from same vendor** (Main Street Tacos): Note which version is correct and why
- **Transit/shipping damage** (Moon Express): Different cause of loss language, BOL documentation
- **Warranty voiding** (CJ Shaughnessy): When manufacturer voids warranty due to damage, document the email/communication
- **Combined claims** (Spare Time Inc #1 and #2): Same insured, different claim numbers, separate reports
- **No cost breakdown available**: Use proportionate-to-original-cost method (Bay Crane radiator pattern)

---

## Workflow Pipeline (To Be Built)

### Input
Emma provides a zip file for each claim containing:
- Assignment PDF(s)
- MIW PDF
- File Notes Worksheet (DOCX) - the primary source of investigation narrative
- Vendor proposals/invoices (PDF)
- Photos (JPG/PNG/BMP or compiled in DOCX)
- Price check screenshots (in subfolder)
- Partially-filled Report Format (DOCX) - sometimes included

### Processing (Subagent Orchestration)
1. **Extract & Parse** - Unzip, identify file types, extract text from PDFs/DOCX/XLSX
2. **Build Claim Profile** - Matter#, Claim#, Insured, Adjuster, Date of Loss, Cause of Loss, Equipment details
3. **Analyze File Notes** - Parse call log, extract contacts, timelines, findings
4. **Analyze Spreadsheet** - Extract cost data, depreciation calculations, vendor breakdowns
5. **Cross-reference** - Verify numbers between notes, spreadsheet, and invoices
6. **Generate Report** - Using template structure and style rules
7. **Generate Invoice Summary** - Using time data from File Notes with rounding rules

### Output
- Draft Report (DOCX/PDF format matching LSG template)
- Draft Invoice Summary (XLSX matching standard format)
- Both pushed to GitHub as a PR for Emma's review

---

## Key Contacts Referenced in Reports

| Name | Role | Contact |
|------|------|---------|
| Tanner Beuret | Technical Consultant, LSG (report author) | (866) 899-8756 ext 755, tbeuret@losssolutionsgroup.com |
| Nick Ramos | Team Leader, LSG | (866) 899-8756 ext 724, nramos@losssolutionsgroup.com |

## Vendor Reference Contacts (from template)
- **Gilbarco gas pumps/DEF equipment**: Jason Paul, Paul and Associates Inc., (909) 391-3889
- **Carrier units**: (listed in template, details to be extracted)
- **Trane units**: (listed in template, details to be extracted)
- **Diesel generators**: (listed in template, details to be extracted)
- **Transformers**: (listed in template, details to be extracted)

---

## TODOs for Next Session

1. Build the subagent orchestration system (CLAUDE.md, processing scripts)
2. Create report generation templates as structured prompts
3. Process the 6 pending claims from Email #3
4. Determine if notes.zip needs to be re-obtained from Tanner
5. Build the GitHub PR workflow for draft delivery
6. Test the pipeline end-to-end with one of the 16 sample bundles
