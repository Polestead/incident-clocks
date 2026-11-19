# Incident clocks

An open dataset of regulatory incident-notification deadlines: when an incident must be
reported, to whom, and what starts the clock. One row per deadline, each with a link to the
statute and the day the row was last checked against that source.

Maintained by [Polestead](https://polestead.com), a trading name of Sri Lux Inc.

## Status

**No release yet.** A row is published only after the quoted statute text has been confirmed
at its source and a person has signed off the passage. Until every row passes, this
repository holds no data. The first release will add `incident-clocks.csv` and
`incident-clocks.json`.

## What a row will contain

| Column | Meaning |
|---|---|
| `framework_code`, `framework` | A short code and the full name of the law or rule |
| `jurisdiction` | Country or region code; a state or province follows a hyphen |
| `trigger` | What starts the clock |
| `stage` | Initial, intermediate or final report |
| `deadline_hours` | Hours allowed for that stage; empty when the rule sets no fixed number of hours |
| `what_is_due`, `authority` | What must be sent, and to whom |
| `legal_reference`, `statute_url` | The article or section, and a link to the source |
| `last_verified` | The day the row was last checked against that source |
| `in_force` | False when the duty is not yet in force |

## How rows are checked

Each deadline is pinned to a short passage quoted from the law or the regulator's own page.
A scheduled check fetches every source, reduces the page to plain text by one fixed rule and
looks for each passage word for word; it also compares the hours in the passage with the
hours in the dataset. No language model is involved. `last_verified` therefore means: the
quoted text was confirmed present at its source on that day, against a passage a person
approved. It does not mean a lawyer re-read the law that day.

## Not legal advice

This is reference information. National rules and regulator guidance can add to or change a
deadline. Read the statute and confirm with counsel before you rely on a date.

## Licence and citation

The data is published under [Creative Commons Attribution 4.0](LICENSE). You may reuse it,
including commercially, if you credit the source. Suggested credit:

> Polestead incident-clock dataset, github.com/Polestead/incident-clocks

## Corrections

If a row is wrong or out of date, open an issue with a link to the source.
