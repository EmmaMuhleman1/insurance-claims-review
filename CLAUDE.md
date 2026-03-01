# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Purpose

This is NOT a software application. It is a **document-processing workflow** for generating insurance claims review reports. Emma works as an independent contractor for Loss Solutions Group, LLC (LSG), reviewing equipment damage claims on behalf of insurance companies. Claude's role is to read claim documentation from zip files and produce finalized reports and invoice summaries matching LSG's required style.

## Key Reference Files

- `3_1_26 help write up reports template.docx` — **The master template.** This is the single most important file. All reports must follow its structure and language patterns. Read it with `python-docx` before generating any report.
- `PROJECT_INDEX.md` — Complete directory index, template structure documentation, depreciation rules, invoice summary specs, and identified variation patterns. **Read this first in any new session.**
- `eight report bundles/` and `another set of eight report bundles/` — 16 complete sample claim bundles (raw inputs + finalized outputs). Use these as ground truth for how inputs map to outputs.
- `random claims (lots)/reports/` — 16 additional finalized report PDFs for style reference.

## Reading Document Files

This repo is almost entirely DOCX, XLSX, and PDF files. Python dependencies needed:

```bash
pip3 install python-docx openpyxl
```

- **DOCX** (File Notes, Report Format, template): Use `python-docx` via Bash
- **XLSX** (Spreadsheets, Invoice Summaries): Use `openpyxl` via Bash
- **PDF** (Assignments, MIW, vendor invoices, finalized reports): Use the Read tool directly (it handles PDFs natively)
- **Photos** (JPG, PNG, BMP): Use the Read tool directly (multimodal)

## Report Generation Rules

### Mandatory Style
- Always use **"reportedly"** when describing the claimed event — LSG is not making the claim
- Write in **simple, direct language** — never sound AI-generated or overly formal
- Be **vague on component specifics** (e.g., "various sizes of pipe" not "1-inch, 1.5-inch, and 2-inch pipe")
- Keep the Cost Analysis section brief — just list what's included, state it's fair and reasonable

### Report Sections (strict order)
Assignment → Findings and Analysis → Scope of Damage → Age & Condition → Cause of Loss → Reparability → Cost Analysis (per-vendor) → RCV → ACV → Salvage → Summary

### Conditional Logic
- **Hartford claims** → Salvage says: "Please refer to your internal salvage department to assess the salvage potential"
- **All other claims** → Salvage says: "Loss Solutions Group submits that there is little to no salvage value associated with this claimed event"
- **New/unused equipment** → Skip ACV entirely: "Loss Solutions Group has not completed an actual cash value (ACV) analysis for this claimed event, as the equipment was in new and unused condition"
- **Lump sum vendor costs** → Must be broken down with vendor help. Note the lump sum in the spreadsheet's NOTES column.

### Depreciation (Spreadsheet)
- Formula: `Depreciation% = Age / Useful Life`, capped at **75% max**
- **Materials** get depreciated; **labor, permits, disposal** are N/A (no depreciation)
- ACV = RCV - Depreciation for each line item

### Invoice Summary
- Rate: **$175/hr**, hours rounded **UP** to nearest **0.25hr** (15-min increment)
- Activity categories: File Review & Client Contact, Insured, Vendors, Research & Technical Analysis, Report & Spreadsheet
- Estimate time from File Notes Worksheet timestamps — add 10 minutes buffer, then round up

## Claim Bundle Structure

Each claim zip typically contains:
- **File Notes Worksheet** (.docx) — PRIMARY source: raw call notes, timestamps, investigation diary
- **SPREADSHEET** (.xlsx) — Cost analysis with CLAIM PRESENTED vs LSG RESEARCHED RCV
- **Assignment/MIW** (.pdf) — Claim metadata (adjuster, insured, dates, claim number)
- **Info PDFs** — Vendor proposals, invoices, emails
- **Photos** — Damage evidence
- **PRICE CHECK/** subfolder — Screenshots of online price research
- **Report Format** (.docx) — Sometimes included as partially-filled template
- **Invoice Summary** (.xlsx) — Billing hours breakdown

## Processing a New Claim

1. Extract the zip and inventory all files by type
2. Read the MIW/Assignment PDF for: Matter#, Claim#, Insured name, Adjuster name/address, Date of Loss, insurance company (Hartford vs other)
3. Read the File Notes Worksheet for: all contact narratives, timestamps, findings
4. Read the Spreadsheet for: vendor names, line items, costs, depreciation, RCV/ACV totals
5. Read vendor Info PDFs for: proposal/invoice numbers, amounts, scope of work
6. Cross-reference totals between spreadsheet and report
7. Generate the report following template structure
8. Generate the invoice summary from File Notes timestamps

## Context Window Management

Claim bundles contain many large files. To stay within limits:
- Use **subagents** (Agent tool) for per-bundle processing — each bundle gets a clean context
- Push intermediate analysis to git (or write to markdown files) before context fills
- The orchestrator agent should coordinate, not read every file itself
- For the 16 sample bundles, reference `PROJECT_INDEX.md` rather than re-reading them all

## Git Workflow

- Remote: `https://github.com/EmmaMuhleman1/insurance-claims-review.git` (private)
- Push requires: `gh auth setup-git` first (gh is at `/opt/homebrew/bin/gh`)
- Draft reports should be pushed as PRs for Emma's review
