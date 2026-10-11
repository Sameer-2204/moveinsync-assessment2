# WorkInSync case-submission package

## Deliverables

| File | Purpose |
|---|---|
| `WorkInSync_Case_Writeup.pdf` | Executive answer plus KPI/implementation appendix |
| `WorkInSync_Case_Writeup.md` | Editable source for the write-up |
| `WorkInSync_Seat_Model.xlsx` | Formula-driven seat model and KPI scorecard template |
| `WorkInSync_Case_Deck.pdf` | Six-slide summary deck |
| `seat-calculator.html` | Self-contained offline calculator; open locally in a browser |

## Final verification

`python scripts/verify_final.py` rebuilds the three generated artifacts and checks the fixture values, workbook XML/formula wiring, PDF page structures, calculator formula markers, and required disclosures.

The environment has no Excel, LibreOffice, or available browser renderer. Structural checks passed; before submission, open the workbook in Excel/Google Sheets, open both PDFs, and open the calculator locally to confirm visual rendering on the chosen sharing platform.


No secrets or personal data are included in these files.
