# Sample Bundle Analysis: Input-to-Report Mapping

This document provides a detailed analysis of how finalized LSG reports are generated from their input files. Two complete bundles are analyzed end-to-end.

---

## BUNDLE 1: Main Street Tacos LLC (427800.16574-00)

### Input Files Inventory
1. **MIW** (Matter Information Worksheet) - PDF, 2 pages
2. **File Notes Worksheet** - .docx with tables of call logs
3. **SPREADSHEET** - .xlsx with pricing breakdowns
4. **Info - cooler invoice.PDF** - Ice Berg Invoice #3422
5. **Info - vent hood estimate.PDF** - RNP Sheetmetal Proposal #1380
6. **docs from vendor/(Correct Proposal) # 1479** - Updated RNP Sheetmetal Proposal #1479
7. **Invoice Summary** - .xlsx with billing hours
8. **Finalized Report** - PDF dated 2-10-26, 4 pages of report text + spreadsheet pages + price check pages

---

### SECTION-BY-SECTION MAPPING

#### 1. LETTERHEAD & HEADER (Page 1 top)
**Exact text:**
```
February 10, 2026

Ms. Ashlee Thompson
The Hartford
690 Asylum Avenue
Hartford, CT 06155

RE:  Insured:             Main Street Tacos LLC
     Claim Number:        CP0021307830
     LSG Matter Number:   427800.16574-00
     Date of Loss:        November 21, 2025
```

**Source mapping:**
- Date: The report date (manually set by consultant, here 2/10/26)
- Adjuster name ("Ms. Ashlee Thompson"): From MIW -> Adjuster section -> "Ms. Ashlee Thompson"
- Company ("The Hartford"): From MIW -> Adjuster -> Company
- Address: From MIW -> Adjuster -> Address ("690 Asylum Avenue / Hartford, CT 06155")
- RE block: All from MIW header fields (Insured, Claim Number, LSG Matter ID, Date of Loss)
- Date of Loss is spelled out: "November 21, 2025" (MIW has "11/21/2025")

**Pattern:** The adjuster honorific "Ms." comes from the MIW which lists "Ms. Ashlee Thompson".

#### 2. OPENING PARAGRAPH
**Exact text:**
```
Dear Ms. Thompson,

Thank you for choosing Loss Solutions Group as your equipment loss consultant. This report
provides an analysis of the above-referenced claim.
```

**Source mapping:**
- Salutation uses adjuster's LAST NAME only: "Ms. Thompson" (derived from MIW adjuster name)
- Opening paragraph is BOILERPLATE - identical across reports. Two variants observed:
  - "This report provides an analysis of the above-referenced claim."
  - "This report serves to provide an analysis of the above-referenced claim."

#### 3. ASSIGNMENT SECTION
**Exact text:**
```
Assignment:

Loss Solutions Group was contacted by Ms. Ashlee Thompson of The Hartford. The scope of this
assignment was to assess the extent of damage and salvage value associated with the insured's Econ
Air-branded kitchen vent hood and related items, along with a walk-in cooler unit. Both items were
reported to have sustained damage during a fire event on November 21, 2025.
```

**Source mapping:**
- "Ms. Ashlee Thompson of The Hartford" -> MIW Adjuster name + Company
- "Econ Air-branded kitchen vent hood" -> From File Notes (vendor call: "They build the hoods Econ air is what was there before") and MIW Property Desc ("vent hood and cooler")
- "walk-in cooler unit" -> MIW Property Desc ("vent hood and cooler")
- "fire event on November 21, 2025" -> MIW Date of Loss + Damage Type
- Investigation scope items ("extent of damage and salvage value") -> derived from MIW Investigation checkboxes (Scope of Damage: Yes, Salvage Market: Yes, ACV: Yes, RCV: Yes)

**Pattern:** "Loss Solutions Group was contacted by [Adjuster Title+Name] of [Company]. The scope of this assignment was to [assess/address] the [extent of damage / salvage value / repair-replacement costs] associated with the insured's [equipment description], reportedly [related to / sustained damage during] a [damage type] event on [Date of Loss spelled out]."

#### 4. FINDINGS AND ANALYSIS SECTION
**Exact text (full):**
```
Findings and Analysis:

Loss Solutions Group contacted the insured, Mr. Frank Alanzo with Main Street Tacos LLC (817-
726-5533), to discuss his role in the claim. Mr. Alanzo explained there was a fire in his kitchen that
caused severe damage to his vent hood, high voltage electrical wiring, the stainless-steel panels for
the walls under the hood, fire insulation, and grease ductwork. Mr. Alanzo further explained how his
walk-in cooler's compressor sustained damage during the fire from shorting out wires running
power to its compressor.

Loss Solutions Group contacted the insured's sheet metal repair vendor, RNP Sheetmetal (214-213-
0322), and spoke with Mr. Rick Pineda to discuss the claimed event and their proposed repairs.
After reviewing the proposal submitted by the insured (Proposal #1380), Mr. Pineda clarified that it
was the incorrect version and instructed us to refer to Proposal #1479 instead. He provided a copy of
the corrected proposal for our reference. Mr. Pineda explained that a fire in the kitchen caused
significant damage to the vent hood, the surrounding walls, some grease ducting above the grill, and
the insulation around the ducting, all of which necessitated replacement.

Loss Solutions Group attempted to contact the insured's HVAC repair vendor, Ice Berg (817-551-
8080 and esmeralda@iceberg.outlook.com), but encountered difficulties reaching someone using the
phone number and email address provided at the top of the invoice. The phone number listed
actually belonged to an Alcon Vision Center, and we did not receive any response to our email
inquiry.

While searching for the correct contact information on Yelp, we found another number listed (817-
902-9621), but that was also disconnected. The Better Business Bureau listed the correct number as
817-920-9950, which we confirmed to be the office number for Ice Berg.

Loss Solutions Group spoke with Ms. "Andrea", who informed us that she could not locate the
referenced invoice (#3422) in their records. She requested that we email her a copy of the invoice so
they could verify it in their system. Ms. "Andrea" later replied, stating, "This invoice was not
created by us, and we do not have Main Street Tacos in our system."

Subsequently, Loss Solutions Group asked the insured for the contact information he had used and
the name of the person he spoke with. The insured provided us with the contact information for Mr.
Manuel Perez (817-851-3818). We spoke with Mr. Perez about the claimed event and the repairs he
had already completed. Mr. Perez explained that when he assessed the insured's walk-in cooler, he
discovered the compressor was shorted out to ground due to melted wires from the fire, resulting in a
power surge necessitating its replacement.

A total amount of $16,476.88 was presented.
```

**Source mapping - Contact by contact:**

**Insured contact paragraph:**
- "Mr. Frank Alanzo" -> File Notes Row 3 ("He called back. Frank Alanzo")
- Phone "817-726-5533" -> File Notes Row 3 (Cell: 817-726-5533) -- NOTE: this is his CELL number from file notes, NOT the business number from MIW (817-709-9929)
- "to discuss his role in the claim" -> STANDARD PHRASE for insured contacts
- Fire damage details -> File Notes Row 3 ("cought on fire", "Fire started on the grill and venihood")
- Walk-in cooler details -> File Notes Row 3 ("THE WIRES SHORTED OUT AND MELTED DUE TO THE FIRE IN THE KITCHEN")

**Vendor 1 (RNP Sheetmetal) paragraph:**
- "insured's sheet metal repair vendor" -> contextual description from file notes
- "RNP Sheetmetal (214-213-0322)" -> File Notes Row 4 ("Rick Pineda / 214-213-0322") -- uses Rick's DIRECT number, not the company main line from MIW (972-329-8288)
- "Mr. Rick Pineda" -> File Notes Row 4
- "Proposal #1380... incorrect version... Proposal #1479" -> File Notes Row 4 ("He found UPDATED quote: 1479" and "Wrong proposal was sent to me")
- Damage description -> File Notes Row 4 combined with vendor proposal content

**Vendor 2 (Ice Berg) paragraphs - COMPLEX NARRATIVE:**
- Phone/email from invoice header -> Info - cooler invoice.PDF (817-551-8080, esmeralda@iceberg.outlook.com)
- "Alcon Vision Center" -> File Notes Row 5 ("Andrew. Alcon vision. Wrong number.")
- Yelp number "817-902-9621" -> File Notes Row 5 (listed but crossed out)
- BBB number "817-920-9950 (office)" -> File Notes Row 5
- "Ms. Andrea" -> File Notes Row 5 ("I spoke with Ms. Andrea")
- Andrea's quote "This invoice was not created by us..." -> File Notes Row 8 ("EMAILED ME SAYING THAT THE QUOTE I HAVE IS NOT FROM THEM") -- formalized/expanded in report
- "Mr. Manuel Perez (817-851-3818)" -> File Notes Row 5 ("Manuel Perez / 817-851-3818")
- Compressor diagnosis -> File Notes Row 5 ("Compressor Tripped. Electrical shortage") expanded into formal language

**Total presented line:**
- "$16,476.88" -> SPREADSHEET total: $13,500.00 (RNP) + $2,976.88 (Ice Berg) = $16,476.88

**KEY PATTERN:** Each contact from the File Notes gets its own paragraph(s) starting with "Loss Solutions Group contacted..." or "Loss Solutions Group spoke with...". The raw shorthand notes are FORMALIZED into professional prose. Phone numbers used are the DIRECT/PERSONAL numbers discovered during investigation, not necessarily the MIW-listed numbers.

#### 5. SCOPE OF DAMAGE SECTION
**Exact text:**
```
Scope of Damage

Loss Solutions Group submits that the insured's Econ Air-branded kitchen vent hood and related
items, along with a walk-in cooler unit, were damaged. The items reportedly sustained damage
during a fire event on November 21, 2025.
```

**Source mapping:**
- Equipment description echoes the Assignment section
- Damage type and date from MIW
- This is largely a RESTATEMENT of the Assignment paragraph's equipment/damage info

**Pattern:** "Loss Solutions Group submits that the insured['s / reportedly sustained significant damage to their] [equipment description][, were damaged / ]. The items reportedly sustained damage during a [damage type] event on [Date of Loss]."

#### 6. AGE & CONDITION SECTION
**Exact text:**
```
Age & Condition

The insured reported that the affected equipment was around one and one-half (1.5) years old and in
average condition at the time of the claimed event.
```

**Source mapping:**
- "one and one-half (1.5) years old" -> File Notes Row 3 ("Age of walk in cooler compressor: roughly 1.5 years old") and Row 3 ("Duct. roughly 1.5 years old")
- "average condition" -> SPREADSHEET Condition column (all items marked "AVERAGE")
- Age is SPELLED OUT with decimal in parentheses: "one and one-half (1.5)"

**Pattern:** "The insured reported that the affected equipment was around [age spelled out] ([age decimal]) years old and in [condition] condition at the time of the claimed event."

#### 7. COST ANALYSIS SECTION
**Exact text:**
```
Cost Analysis

Loss Solutions Group assessed the proposed costs by cross-referencing with alternative vendors,
drawing on historical data for similar repairs, evaluating comparable equipment pricing, and
consulting directly with the involved vendor to verify reasonableness.
```

**Source mapping:**
- This is BOILERPLATE. Two variants observed:
  - Variant A (Main Street Tacos): "Loss Solutions Group assessed the proposed costs by cross-referencing with alternative vendors, drawing on historical data for similar repairs, evaluating comparable equipment pricing, and consulting directly with the involved vendor to verify reasonableness."
  - Variant B (Bourbon Grill): "Loss Solutions Group has researched the costs using alternate vendor resources, historical references, similar equipment costs, and vendor experience and we have discussed the pricing with the vendor involved. The following is a breakdown of the associated costs."

#### 8. VENDOR COST BREAKDOWN SUB-SECTIONS
**For RNP Sheetmetal:**
```
RNP SHEETMETAL (972-329-8288) PROPOSAL # 1479

Loss Solutions Group reviewed the proposal presented by RNP Sheetmetal totaling $13,500.00 for
the replacement of the insured's vent hood and related items.

Included in the cost is an amount for a ten foot (10') long type 1 vent hood with lights and filters,
stainless steel panels, some grease ducting, and double-layered fire wrap for the grease duct. We
submit that these components are required to complete the repairs, and the costs are fair and
reasonable.

Loss Solutions Group has reviewed the labor costs for the vendor to diagnose the damage and to
perform the repairs. We submit that these amounts are fair and reasonable to complete the scope of
work as presented to us.
```

**Source mapping:**
- Header "RNP SHEETMETAL (972-329-8288) PROPOSAL # 1479" -> SPREADSHEET section header (uses the COMPANY main number 972-329-8288, not Rick's personal number)
- "$13,500.00" -> SPREADSHEET: Claim Presented Total for RNP section = $13,500.00
- Item descriptions -> SPREADSHEET Notes column + vendor proposal: "10 FOOT TYPE 1 VENT HOOD WITH LIGHTS AND FILTERS", "STAINLESS STEEL PLATES", "DUCTWORK", "DOUBLE LAYER FIRE WRAP"
- Numbers are SPELLED OUT: "ten foot (10')"

**For Ice Berg:**
```
ICE BERG (817-851-3818) INVOICE # 3422

Loss Solutions Group reviewed the invoice presented by Ice Berg totaling $2,976.88 for the repairs
to the insured's walk-in cooler.

Included in the cost is an amount for a Copeland-branded scroll compressor, a liquid line filter,
copper connections, and brazing materials. We submit that these components were required to
complete the repair, and the costs are fair and reasonable.

Loss Solutions Group has reviewed the labor costs for the vendor to diagnose the damage and to
perform the repairs. We submit that these amounts are fair and reasonable to complete the scope of
work as presented to us.
```

**Source mapping:**
- Header uses "(817-851-3818)" -> This is Manuel Perez's number (the actual repair person), matching SPREADSHEET header
- "$2,976.88" -> SPREADSHEET: Total for Ice Berg section (Sub-total $2,750 + Sales Tax $226.88)
- "Copeland-branded scroll compressor, a liquid line filter, copper connections, and brazing materials" -> SPREADSHEET Notes for Row 3: "ONE SCROLL COMPRESSOR (COPELAND BRANDED), LIQUID LINE FILTER DRYER, BRAZING MATERIALS, ELECTRICAL WIRE, ELECTRICAL CONNECTIONS, ETC."

**Pattern for each vendor section:**
```
[VENDOR NAME] ([PHONE]) [PROPOSAL/INVOICE] # [NUMBER]

Loss Solutions Group [reviewed/has reviewed] the [proposal/invoice/amount] presented by [Vendor] totaling $[total] for the [replacement/repairs] [of/to] the insured's [equipment].

Included in the cost is an amount for [list of key components from spreadsheet Notes]. We submit that these components [are/were] required to complete the [repair/repairs/replacement], and the costs are fair and reasonable.

Loss Solutions Group has reviewed the labor costs for the vendor to diagnose the damage and to perform the repairs. We submit that these amounts are fair and reasonable to complete the scope of work as presented to us.
```

#### 9. RCV SECTION
**Exact text:**
```
RCV

Loss Solutions Group submits an amount of $16,476.88 (RCV) as being fair and reasonable to return
the insured to a pre-loss condition. A further breakdown of the pricing is available in the attached
spreadsheet.
```

**Source mapping:**
- "$16,476.88" -> SPREADSHEET: TOTAL RESEARCHED RCV = $16,476.88

**Pattern:** "Loss Solutions Group submits an amount of $[RCV] (RCV) as being fair and reasonable to return the insured to a pre-loss condition. A further breakdown of the pricing is available in the attached spreadsheet."

#### 10. ACV SECTION
**Exact text:**
```
ACV

Loss Solutions Group submits an actual cash value (ACV) amount of $15,407.81 based on linear age
depreciation of the materials only. We estimate the average life expectancy of the equipment to be
around twenty (20) years.
```

**Source mapping:**
- "$15,407.81" -> SPREADSHEET: TOTAL ACV = $15,407.81
- "twenty (20) years" -> SPREADSHEET: Useful Life column (all depreciable items show 20 years)
- When all items share the same useful life -> "the average life expectancy of the equipment to be around [life] years"
- When items have DIFFERENT useful lives -> "the average life expectancy of the equipment varies based on the equipment type. A further breakdown of this is available in the attached spreadsheet."

**Pattern:** "Loss Solutions Group submits an actual cash value (ACV) amount of $[ACV] based on linear age depreciation of the materials only. We estimate [the average life expectancy of the equipment to be around [life spelled out] ([life]) years / that the average life expectancy of the equipment varies based on the equipment type. A further breakdown of this is available in the attached spreadsheet]."

#### 11. SALVAGE SECTION
**Exact text:**
```
Salvage

Please refer to your internal salvage department to assess the salvage potential.
```

**Source mapping:**
- When MIW Investigation has "Salvage Market: Yes" but no specific salvage finding -> "Please refer to your internal salvage department to assess the salvage potential."
- Alternative (when there is no salvage): "Loss Solutions Group submits that there is little to no salvage value associated with this claimed event."

#### 12. SUMMARY SECTION
**Exact text:**
```
Summary:

Loss Solutions Group's findings herein are based upon all information that was available at the time
of this writing. The opinions are based upon reviewed documentation, interviews, research,
experience, historical references, training and education.

1. The insured, Main Street Tacos LLC, reported damages to their Econ Air-branded kitchen
   vent hood and related items, along with a walk-in cooler unit. The items reportedly sustained
   damage during a fire event. A total amount of $16,476.88 was presented.

2. The insured reported that the affected equipment was around one and one-half (1.5) years old
   and in average condition at the time of the claimed event.

3. Loss Solutions Group submits an amount of $16,476.88 (RCV) as being fair and reasonable
   to return the insured to a pre-loss condition. A further breakdown of the pricing is available
   in the attached spreadsheet.

4. Loss Solutions Group submits an ACV amount of $15,407.81 based on linear age
   depreciation of the materials only.

5. Please refer to your internal salvage department to assess the salvage potential.
```

**Source mapping:**
- Opening paragraph is BOILERPLATE (identical across all reports)
- Item 1 = condensed version of Scope of Damage + total presented amount
- Item 2 = exact copy of Age & Condition section
- Item 3 = exact copy of RCV section
- Item 4 = condensed ACV (may omit life expectancy detail)
- Item 5 = Salvage section

**Note:** Reparability item is OMITTED here because MIW has "Reparability: No" (not part of scope).

#### 13. CLOSING / SIGNATURE BLOCK
**Exact text:**
```
If you have any questions or if you need any additional information, please feel free to
contact Tanner Beuret at (866) 899-8756 ext. 755, or via email at
tbeuret@losssolutionsgroup.com. Team Leader Nick Ramos can be reached at (866) 899-
8756 ext. 724, or via email at nramos@losssolutionsgroup.com.

Best regards,

[signature]

Tanner Beuret
Technical Consultant
Loss Solutions Group, LLC
```

**Source mapping:**
- Consultant name "Tanner Beuret" -> MIW "Assigned To: Beuret, Tanner"
- Extension numbers are specific to each consultant (755 for Tanner Beuret)
- Team Leader name -> from internal records (Nick Ramos, ext 724)

#### 14. PAGE HEADERS (Pages 2+)
**Exact text:**
```
Insured: Main Street Tacos LLC                                     Page 2
Claim Number: CP0021307830
LSG Matter Number: 427800.16574-00
```
- All from MIW header fields

---

## BUNDLE 2: BOURBON GRILL & MORE, LLC (787200.11940-00)

### Input Files Inventory
1. **MIW** - PDF, 2 pages
2. **File Notes Worksheet** - .docx
3. **SPREADSHEET** - .xlsx with 3 vendor sections
4. **Info 1.pdf** - Assignment/initial docs
5. **Info 2.pdf** - Additional docs
6. **docs from adjuster/ECFS-Quote** - East Georgia Fire & Safety quote ($4,550)
7. **docs from EF vendor/DSIZE-Master-BourbonGrill.pdf** - Econ-Air master drawing/specs (8 pages)
8. **Photos from insured.docx** - Photos of damage
9. **Photos (1-4).jpg** - Individual damage photos
10. **Invoice Summary** - .xlsx
11. **Finalized Report** - PDF dated 2-10-26, 5 pages + spreadsheet pages + price check pages

---

### SECTION-BY-SECTION MAPPING

#### 1. LETTERHEAD & HEADER
**Exact text:**
```
February 10, 2026

Ms. Olivia Williams
Travelers Insurance
P.O. Box 430
Buffalo, NY 14240-0430

RE:  Insured:             BOURBON GRILL & MORE, LLC
     Claim Number:        DFZ8759
     LSG Matter Number:   787200.11940-01
     Date of Loss:        February 2, 2025
```

**Source mapping:** All from MIW. Note the matter number in the report is "787200.11940-**01**" (supplemental) while MIW shows "787200.11940-**00**" (original).

#### 2. OPENING PARAGRAPH
**Exact text:**
```
Dear Ms. Williams,

Thank you for choosing Loss Solutions Group as your equipment loss consultant. This report serves
to provide an analysis of the above-referenced claim.
```

**Note:** Uses variant "serves to provide" instead of just "provides" -- slight variation from Bundle 1.

#### 3. ASSIGNMENT SECTION
**Exact text:**
```
Assignment:

Loss Solutions Group was contacted by Ms. Olivia Williams of Travelers Insurance. The scope of
this assignment was to address the extent of damage, salvage value, and repair / replacement costs
associated with the insured's damaged commercial kitchen exhaust system and hood, reportedly
related to a fire event on February 2, 2025.
```

**Source mapping:**
- "Ms. Olivia Williams of Travelers Insurance" -> MIW Adjuster
- "extent of damage, salvage value, and repair / replacement costs" -> derived from MIW Investigation checkboxes (Scope of Damage: Yes, Salvage Market: Yes, ACV: Yes, RCV: Yes)
- "commercial kitchen exhaust system and hood" -> MIW Property Type ("Commercial Kitchen/Restaurant Equipment - Exhaust hood")
- "fire event on February 2, 2025" -> MIW Date of Loss + Damage Type

#### 4. FINDINGS AND ANALYSIS
**Exact text (full):**
```
Findings and Analysis:

Loss Solutions Group contacted the insured, Mr. Van Lu with Bourbon Grill & More, LLC (912-
536-9770), to advise him of our involvement in reviewing this claimed event. During our
conversation, Mr. Lu explained that on February 2, 2025, their kitchen's stove was left on maximum
heat for a second while some ingredients were being gathered, and when they came back to it the
back wall had caught on fire and traveled upwards. The fire was reportedly contained in the hood
and fire was being sucked up and out of the building completely melting and destroying the hood,
ductwork, the make-up air fan, and the exhaust fan on the roof.

Loss Solutions Group contacted the insured's hood and exhaust fan vendor, T.M.G. Contracting
(912-663-1227), and spoke with Mr. Thomas Canady to discuss the claimed event and their
proposal. The vendor reported that due to the fire, damages were beyond repair and required a full
replacement of the hood, ductwork, supply and exhaust fans. Mr. Canady went on to detail the parts
needed for the job to help in breaking their costs down.

Loss Solutions Group contacted the insured's fire suppression vendor, East Georgia Fire & Safety
(912-690-2527), and spoke with Mr. Brian Persinger to discuss their quote. The vendor reported that
the system would need a new 4.6 gallon Pyrochem bottle/wet chemical, fusible fire links, and nine
(9) new blow away fire suppression heads.

Loss Solutions Group contacted the insured's fire suppression vendor, East Georgia Fire & Safety
(912-690-2527), and spoke with Mr. Brian Persinger regarding the two (2) new invoices that had
been submitted to us. The first invoice, dated January 14, 2026, was explained by Mr. Persinger as
the remaining balance for the job that had already been completed, and not a bill for any new work.
The second invoice, dated November 6, 2025, was for additional work to relocate two (2) fire
sprinkler heads. Mr. Persinger clarified that this adjustment was necessary due to the installation of a
new hood that was slightly larger than the previous unit. As a result, the fire sprinkler heads needed
to be moved a few feet to align properly with the drop ceiling tiles.

A total amount of $38,575.00 was presented.
```

**Source mapping - Contact by contact:**

**Insured (Mr. Van Lu):**
- "Mr. Van Lu with Bourbon Grill & More, LLC (912-536-9770)" -> MIW Contacts (Cell: 912-536-9770)
- "to advise him of our involvement in reviewing this claimed event" -> STANDARD PHRASE variant for insured
- Fire narrative -> File Notes Row 3: "Kitchen Stove turned on to MAX, we walked away for a sec, back wall started on fire and then travled up. Contained within the hood."
- Damage details ("completely melting and destroying the hood, ductwork, the make-up air fan, and the exhaust fan on the roof") -> File Notes Row 3 combined with vendor details

**Vendor 1 (T.M.G. Contracting):**
- "T.M.G. Contracting (912-663-1227)" -> MIW Vendor Contact
- "Mr. Thomas Canady" -> File Notes Row 4 and MIW (Contact: Thomas Canady, President)
- "damages were beyond repair and required a full replacement" -> File Notes Row 4
- "detail the parts needed for the job to help in breaking their costs down" -> references the cost breakdown process documented in File Notes

**Vendor 2 (East Georgia Fire & Safety):**
- "East Georgia Fire & Safety (912-690-2527)" -> File Notes Row 5
- "Mr. Brian Persinger" -> File Notes Row 5
- "4.6 gallon Pyrochem bottle/wet chemical, fusible fire links, and nine (9) new blow away fire suppression heads" -> File Notes Row 5 ("Pyrochem system. Johnson controls. 4.6 gallon system. 1 bottle. Chem: wet chemical. Parts: fusable link, the nozles have blow away heads on them. 9 of them.")
- Second EGFS paragraph about two new invoices -> from the additional work orders (pages 9-10 of report PDF: work orders dated 1/14/26 and 11/6/25)

**Total presented:**
- "$38,575.00" -> SPREADSHEET: $33,000 + $4,550 + $1,025 = $38,575.00

#### 5. SCOPE OF DAMAGE
**Exact text:**
```
Loss Solutions Group submits that the insured reportedly sustained significant damage to their
commercial kitchen exhaust system and hood, reportedly related to a fire event on February 2, 2025.
```

**Note:** Uses "reportedly sustained significant damage" instead of listing specific items -- slightly different pattern from Bundle 1.

#### 6. AGE & CONDITION
**Exact text:**
```
The insured reported that the affected equipment was around twenty-one (21) years old and in
average condition at the time of the claimed event.
```

**Source:** File Notes Row 3 ("Age: 21 years old") + SPREADSHEET Age column (21 years) + Condition column ("AVERAGE")

#### 7. REPARABILITY (NEW SECTION - not in Bundle 1)
**Exact text:**
```
Reparability

Loss Solutions Group has reviewed the information provided, and we have discussed the damage
with the vendor involved. We submit that the proposed replacement path is warranted due to the
extent of damage reportedly sustained during the claimed event.
```

**Source:** This section appears because the damage was extensive enough to warrant replacement discussion. File Notes show vendor saying equipment is beyond repair. MIW Investigation has "Reparability: No" (meaning it was NOT in the original scope checklist), yet the report includes it -- likely because the adjuster's notes said "Mainly looking for validation."

#### 8. COST ANALYSIS + VENDOR BREAKDOWNS
Three vendor sections in this report:

**T.M.G CONSTRUCTING (912-663-1227) QUOTE TOTALING $33,000.00**
```
Loss Solutions Group has reviewed the amount of $33,000.00 for the replacement of the insured's
commercial kitchen exhaust system and hood.

Included in the cost is an amount for a new exhaust fan, make-up air fan, 430 stainless steel grease
ductwork from the hood down below to the exhaust fan on the roof (this includes ductwork, elbows,
duct tees, duct adapters, duct collars and duct reducers), support brackets, duct access door, an eight
foot (8') wide kitchen hood, and other miscellaneous other smaller items. We submit these
components are required to complete the replacement and the costs are fair and reasonable.
```
- "$33,000.00" -> SPREADSHEET Claim Presented Total for TMG section
- Component list -> SPREADSHEET items 2-9 Notes column
- "eight foot (8')" -> SPREADSHEET item 9 "8 FOOT HOOD"

**EAST GEORGIA FIRE & SAFETY (912-690-2527) QUOTE TOTALING $4,550.00**
```
Loss Solutions Group has reviewed the amount of $4,550.00 for the replacement of the insured's fire
suppression agent and other miscellaneous items.

Included in the cost is an amount for a 4.6 gallon Pyrochem bottle/wet chemical, fusible fire links,
and nine (9) new blow away fire suppression heads. We submit these components are required to
complete the repair and the costs are fair and reasonable.
```
- "$4,550.00" -> SPREADSHEET + ECFS Quote PDF (Total $4,550)
- Components -> SPREADSHEET items 2-5 of EGFS section

**EAST GEORGIA FIRE & SAFETY (912-690-2527) QUOTE DATED ON NOVEMBER 6, 2025 TOTALING $1,025.00**
```
Loss Solutions Group has reviewed the amount of $1,025.00 for the relocation of two (2) fire
sprinkler heads.

Included in the cost is an amount for cast iron piping and connections. We submit that these
components were required to complete the repair, and the costs are fair and reasonable.
```
- "$1,025.00" -> SPREADSHEET 3rd section total
- "cast iron piping and connections" -> SPREADSHEET Notes for item 2: "PARTS AND MATERIALS: CAST IRON PIPING AND CONNECTIONS, PIPE DOPE, ETC."

#### 9. RCV
- "$38,575.00" -> SPREADSHEET TOTAL RESEARCHED RCV

#### 10. ACV
```
Loss Solutions Group submits an actual cash value (ACV) amount of $29,245.50 based on linear age
depreciation of the materials only. We estimate that the average life expectancy of the equipment
varies based on the equipment type. A further breakdown of this is available in the attached
spreadsheet.
```
- "$29,245.50" -> SPREADSHEET TOTAL ACV
- "varies based on the equipment type" -> because SPREADSHEET has MIXED useful lives (20 years for fans, 50 years for ductwork/hood, 30 years for fire suppression)

#### 11. SALVAGE
```
Loss Solutions Group submits that there is little to no salvage value associated with this claimed
event.
```
- Different from Bundle 1's "refer to internal department" -- here a definitive "little to no salvage" determination was made (likely based on photos showing complete destruction)

#### 12. SUMMARY
6 items (vs 5 in Bundle 1):
1. Equipment/damage/total presented ($38,575.00)
2. Age & Condition (twenty-one (21) years, average)
3. Reparability finding (replacement warranted) -- EXTRA item not in Bundle 1
4. RCV ($38,575.00)
5. ACV ($29,245.50) with note about varying life expectancy
6. Salvage (little to no value)

---

## REPORT GENERATION CHEATSHEET

### OPENING PARAGRAPH TEMPLATE
```
[Report Date spelled out, e.g., "February 10, 2026"]

[Adjuster Honorific + Name]
[Insurance Company]
[Address Line 1]
[Address Line 2]

RE:  Insured:             [Insured Name from MIW]
     Claim Number:        [Claim Number from MIW]
     LSG Matter Number:   [LSG Matter ID from MIW]
     Date of Loss:        [Date of Loss SPELLED OUT, e.g., "November 21, 2025"]

Dear [Adjuster Honorific + Last Name],

Thank you for choosing Loss Solutions Group as your equipment loss consultant. This report
[provides / serves to provide] an analysis of the above-referenced claim.
```

### ASSIGNMENT SECTION TEMPLATE
```
Assignment:

Loss Solutions Group was contacted by [Adjuster Full Name] of [Insurance Company]. The scope
of this assignment was to [assess/address] the [extent of damage[, salvage value,] [and repair /
replacement costs]] associated with the insured's [equipment description from MIW Property Desc +
details from file notes], reportedly [related to / having sustained damage during] a [damage type]
event on [Date of Loss spelled out].
```

**Rules for scope phrase:**
- If MIW Investigation checkboxes = Scope of Damage + ACV + RCV: "assess the extent of damage and salvage value"
- If also includes repair costs: "address the extent of damage, salvage value, and repair / replacement costs"

### FINDINGS SECTION PATTERN

**For EACH contact (insured, then each vendor), write one or more paragraphs:**

**Insured contact:**
```
Loss Solutions Group contacted the insured, [Mr./Ms.] [Full Name] with [Company] ([phone]),
to [discuss his/her role in the claim / advise him/her of our involvement in reviewing this claimed
event]. [During our conversation,] [Mr./Ms. Last Name] explained [narrative of what happened
based on file notes, formalized into professional prose].
```

**Vendor contact:**
```
Loss Solutions Group contacted the insured's [vendor description, e.g., "sheet metal repair vendor"],
[Vendor Company] ([phone]), and spoke with [Mr./Ms.] [Full Name] to discuss the claimed event
and their [proposal/proposed repairs/quote]. [Vendor narrative from file notes, formalized].
```

**If contact difficulties occurred (like Ice Berg), document the full investigation narrative.**

**Close Findings with:**
```
A total amount of $[Total Presented from SPREADSHEET] was presented.
```

### SCOPE OF DAMAGE TEMPLATE
```
Scope of Damage

Loss Solutions Group submits that the insured['s [equipment list] [were/was] damaged /
reportedly sustained significant damage to their [equipment description]]. The items reportedly
sustained damage during a [damage type] event on [Date of Loss].
```

### AGE & CONDITION TEMPLATE
```
Age & Condition

The insured reported that the affected equipment was around [age spelled out] ([age decimal/integer])
years old and in [condition from spreadsheet] condition at the time of the claimed event.
```

**Age spelling rules:**
- 1.5 -> "one and one-half (1.5)"
- 21 -> "twenty-one (21)"
- 3 -> "three (3)"

### REPARABILITY TEMPLATE (only if applicable)
```
Reparability

Loss Solutions Group has reviewed the information provided, and we have discussed the damage
with the vendor involved. We submit that the proposed replacement path is warranted due to the
[extent of / higher extent of] damage reportedly sustained during the claimed event.
```

### COST ANALYSIS SECTION TEMPLATE
**Opening (one of two variants):**
```
Cost Analysis

[Variant A]: Loss Solutions Group assessed the proposed costs by cross-referencing with alternative
vendors, drawing on historical data for similar repairs, evaluating comparable equipment pricing,
and consulting directly with the involved vendor to verify reasonableness.

[Variant B]: Loss Solutions Group has researched the costs using alternate vendor resources,
historical references, similar equipment costs, and vendor experience and we have discussed the
pricing with the vendor involved. The following is a breakdown of the associated costs.
```

**For EACH vendor section in the SPREADSHEET:**
```
[VENDOR NAME (PHONE)] [PROPOSAL/INVOICE/QUOTE] [# NUMBER / TOTALING $X / DATED ON DATE TOTALING $X]

Loss Solutions Group [reviewed the proposal presented by / has reviewed the amount of $X for /
reviewed the invoice presented by] [Vendor] [totaling $X] for the [replacement/repairs/relocation]
[of/to] the insured's [equipment description].

Included in the cost is an amount for [list key components from SPREADSHEET Notes column,
using professional language]. We submit [that] these components [are/were] required to complete
the [repair/repairs/replacement][,] and the costs are fair and reasonable.

Loss Solutions Group has reviewed the labor costs for the vendor to diagnose the damage and to
perform the repairs. We submit that these amounts are fair and reasonable to complete the scope of
work as presented to us.
```

### RCV TEMPLATE
```
RCV

Loss Solutions Group submits an amount of $[TOTAL RESEARCHED RCV from SPREADSHEET]
(RCV) as being fair and reasonable to return the insured to a pre-loss condition. A further breakdown
of the pricing is available in the attached spreadsheet.
```

### ACV TEMPLATE
```
ACV

Loss Solutions Group submits an actual cash value (ACV) amount of $[TOTAL ACV from
SPREADSHEET] based on linear age depreciation of the materials only. We estimate [that] the
average life expectancy of the equipment [to be around [life spelled out] ([life]) years / varies based
on the equipment type. A further breakdown of this is available in the attached spreadsheet].
```

**Rule:** If all depreciable items share ONE useful life -> state it. If items have DIFFERENT useful lives -> use "varies" language.

### SALVAGE TEMPLATE
```
Salvage

[Option A - No specific finding]: Please refer to your internal salvage department to assess the
salvage potential.

[Option B - No salvage]: Loss Solutions Group submits that there is little to no salvage value
associated with this claimed event.

[Option C - Salvage exists]: Loss Solutions Group submits a salvage value of $[amount]...
```

### SUMMARY TEMPLATE
```
Summary:

Loss Solutions Group's findings herein are based upon all information that was available at the time
of this writing. The opinions are based upon reviewed documentation, interviews, research,
experience, historical references, training and education.

1. The insured, [Insured Name], [reported damages to / claimed that] their [equipment list]
   [were damaged / . The items reportedly sustained damage] [during/due to] a [damage type]
   event [on Date of Loss - ONLY in Bourbon Grill version, omitted in Main Street Tacos].
   A total amount of $[Total Presented] was presented.

2. The insured reported that the affected equipment was around [age spelled out] ([age]) years
   old and in [condition] condition at the time of the claimed event.

[3. IF REPARABILITY IN SCOPE: Loss Solutions Group has reviewed the information provided,
   and we have discussed the damage with the vendor involved. We submit that the proposed
   replacement path is warranted due to the [higher] extent of damage reportedly sustained
   during the claimed event.]

[N]. Loss Solutions Group submits an amount of $[RCV] (RCV) as being fair and reasonable
   to return the insured to a pre-loss condition. A further breakdown of the pricing is available
   in the attached spreadsheet.

[N+1]. Loss Solutions Group submits an ACV amount of $[ACV] based on linear age
   depreciation of the materials only. [Life expectancy detail if applicable.]

[N+2]. [Salvage statement.]
```

### CLOSING TEMPLATE
```
If you have any questions or if you need any additional information, please feel free to
contact [Consultant Name] at (866) 899-8756 ext. [ext], or via email at
[email]@losssolutionsgroup.com. Team Leader [TL Name] can be reached at (866) 899-
8756 ext. [TL ext], or via email at [TL email]@losssolutionsgroup.com.

Best regards,

[signature]

[Consultant Name]
Technical Consultant
Loss Solutions Group, LLC
```

### INVOICE SUMMARY PATTERN
The Invoice Summary spreadsheet has these standard activity categories:
1. **File Review & Client Contact** - Time communicating with adjuster
2. **Insured** - Time spent contacting/discussing with insured
3. **Vendors** - Time spent contacting/discussing with vendors
4. **Research & Technical Analysis** - Price checking, technical research
5. **Report & Spreadsheet** - Writing the final report and filling spreadsheet

Pay rate: $175/hour (standard across both bundles)
Mileage: $0.68-$0.70/mile (for any site visits)

---

### KEY OBSERVATIONS

1. **File Notes are the PRIMARY source for Findings narrative.** The raw shorthand notes get formalized into professional prose but the SUBSTANCE (names, phone numbers, what was said) comes directly from file notes.

2. **SPREADSHEET is the PRIMARY source for all financial figures.** The RCV, ACV, Total Presented, and depreciation amounts all come directly from spreadsheet calculations.

3. **MIW provides the framework/metadata.** Adjuster info, claim numbers, insured info, date of loss, property type, investigation scope -- all from MIW.

4. **Phone numbers in the report may differ from MIW.** The report uses DISCOVERED/ACTUAL numbers from the investigation (e.g., Rick Pineda's personal cell rather than RNP's main line in Findings, but RNP's main line in the Cost Analysis header).

5. **The report has TWO different phone number contexts:**
   - In Findings paragraphs: uses the PERSONAL/DIRECT number of the person spoken to
   - In Cost Analysis vendor headers: uses the number from the SPREADSHEET header (usually the company main line or the number on the invoice)

6. **Age is always SPELLED OUT with the number in parentheses.** E.g., "one and one-half (1.5)", "twenty-one (21)".

7. **The Summary section is a numbered list that mirrors the report sections in order:** equipment/damage -> age/condition -> [reparability if applicable] -> RCV -> ACV -> salvage.

8. **Boilerplate phrases are reused consistently** but with minor variations (e.g., "provides" vs "serves to provide", "assessed" vs "has researched").

9. **Vendor doc content (proposals, invoices, quotes) appears in TWO places:**
   - Findings: narrative about what the vendor said/did
   - Cost Analysis: specific cost items and reasonableness assessment

10. **The SPREADSHEET Notes column is the bridge** between raw vendor documents and report language. The notes column contains professionally-worded descriptions of each line item that get pulled into the Cost Analysis section nearly verbatim.
