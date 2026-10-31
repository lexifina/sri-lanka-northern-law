# How this repository was made (Northern Province)

This file is written by the build on 2026-10-31, the day the source data was retrieved.

## Sources

| Source | Address | Retrieved | Licence |
| --- | --- | --- | --- |
| Northern Provincial Council: statutes page, English text of each statute as published in the Gazette Extraordinary (PDF with a text layer) | <https://np.gov.lk/statutes/> | 2026-10-31 | Statutes of the Northern Provincial Council as published in the Gazette of the Democratic Socialist Republic of Sri Lanka (Extraordinary), Part IV (A), and posted on https://np.gov.lk. Intellectual Property Act, No. 36 of 2003 (Sri Lanka), section 8: copyright protection does not extend to any official text of a legislative, administrative or legal nature, or to any official translation of such a text. |
| Northern Provincial Council: statutes page, English text of each statute as published in the Gazette Extraordinary (PDF with a text layer) | <https://np.gov.lk/statutes/> | 2026-10-31 | Statutes of the Northern Provincial Council as published in the Gazette of the Democratic Socialist Republic of Sri Lanka (Extraordinary), Part IV (A), and posted on https://np.gov.lk. Intellectual Property Act, No. 36 of 2003 (Sri Lanka), section 8: copyright protection does not extend to any official text of a legislative, administrative or legal nature, or to any official translation of such a text. |
| Northern Provincial Council: statutes page, English text of each statute as published in the Gazette Extraordinary (PDF with a text layer) | <https://np.gov.lk/statutes/> | 2026-10-31 | Statutes of the Northern Provincial Council as published in the Gazette of the Democratic Socialist Republic of Sri Lanka (Extraordinary), Part IV (A), and posted on https://np.gov.lk. Intellectual Property Act, No. 36 of 2003 (Sri Lanka), section 8: copyright protection does not extend to any official text of a legislative, administrative or legal nature, or to any official translation of such a text. |

Every word of law in this repository comes from these sources. Lexifina reads them and records each act's dated versions, and the laws that made each change, in one corpus file. This repository is built from that file.

## What is in it

| Act | Title | Versions | Span |
| --- | --- | ---: | --- |
| `department-of-probation-and-child-care-services-statute-of-the-northern-province` | Department of Probation and Child Care Services Statute of the Northern Province No. 05 of 2016 | 1 | 2017-03-22 to 2017-03-22 |
| `tranfer-of-court-fines-and-penalties-statute-of-the-northern-province-provincial` | Transfer of Court Fines and Penalties Statute of the Northern Province Provincial Council No. 01 of 2017 | 1 | 2017-07-31 to 2017-07-31 |
| `mineral-tax-statute-no-03-of-2017` | Mineral Tax Statute of the Northern Province Provincial Council No.03 of 2017 | 1 | 2017-09-13 to 2017-09-13 |
| `transfer-of-stamp-duty-statute-of-the-northern-province-no-02-of-2014` | Transfer of Stamp Duty Statute of the Northern Provincial Council No. 02 of 2014 | 1 | 2014-11-27 to 2014-11-27 |
| `northern-province-tourism-bureau-statute-no-02-of-2017` | Northern Province Tourism Bureau Statute No. 02 of 2017 | 1 | 2018-01-15 to 2018-01-15 |
| `education-statute-no-02-of-2015` | Northern Province Education Statute No. 02 of 2015 | 1 | 2016-04-01 to 2016-04-01 |
| `indigenous-medicine-statute-no-09-of-2016` | Northern Province Indigenous Medicine – No. 09 of 2016 | 1 | 2018-04-05 to 2018-04-05 |
| `northern-province-business-names-statute-no-01-of-2018` | Northern Province Business Names Statute No.01 of 2018 | 1 | 2019-02-20 to 2019-02-20 |

The build made 8 commits:

| Commits | Kind |
| ---: | --- |
| 8 | first version of an act |
| 0 | one law on its in-force day |
| 0 | changes no amendment note explains, credited to the publisher |

Other counts:
- 0 commits on the branch `future`: laws not yet in force on 2026-10-31.
- 0 commits dated 1 January 1970: in force before 1970, with the real day in their `In-force` trailer.
- 1 laws in the record.
- 8 tags.

## Dates

Each commit is dated at noon (Asia/Colombo) on the day the change took effect. The other dates, enacted and published, are trailers.

When a law gives no date of its own, the default rule applies: Each statute is dated by the day the Gazette Extraordinary published it; its own section 1 says when it comes into operation (usually on the Governor's assent), which this record does not derive. https://np.gov.lk/statutes/

## How the history is built

`tools/build.py` turns the corpus into this history in one pass: one commit per law, on the day it took effect. The same corpus always gives the same commit hashes. `tools/check_repo.py` reads every version back from git and compares it with the corpus. `tools/on.py` shows the law as it stood on any date. The corpus format is described in `tools/SCHEMA.md`.

- Corpus: sha256 `39305ff8da7a37fe2c3fcde7ddb2025a0980d6b041febc35f2adfc8d92879f1d` (159272 bytes).
- Builder blob hashes (`git hash-object`): `build.py` `35388bee5aa05369f7da68f5a8fa015ea8d442b8`, `check.py` `5d719354ea4c62d240c93d2cae446307d81d9e81`, `on.py` `aff48cf1b68d50c7ba8f399ca32261871c301824`.
- Python 3.14.4; git version 2.53.0.

## Checks

8 versions of 8 acts read back from git on the day each took effect and on the day before: 0 mismatches. Trailers: 0 commits whose trailers git cannot parse. Health: 0 merge commits on main, 0 commit dates that go backwards, 0 commits dated after the build.

No second build of this corpus has been compared yet.

## Decisions made by hand

- Oldest version available: each statute is one version, its English text as published in the Gazette Extraordinary (Part IV (A), Provincial Councils), dated the day of that Gazette (first_law null), credited to the Council, not to an amending law. Amending statutes are recorded as statutes of their own; their changes are not replayed into the statutes they amend.
- English text only. Statutes are enacted in Sinhala and Tamil as well; where a statute says which text prevails, it says so in its own words in this record.
- One file per section where each section starts with its number beside a marginal note (the note is the line after the section label); otherwise one file, 000-text, holding the whole statute from its heading.
- Left out: the Gazette masthead, running heads and the Sinhala/Tamil lines in legacy fonts, page labels, printing footers, the Council Secretary's publication notice, and marginal notes where sections are not split.
- A statute is left out when a second reading of its PDF (pdftotext) does not find every paragraph of the record whole, or finds text in the statute's stretch that the record lacks (tables, forms, layout the parser misreads).
- 20-statutes-02: statutes an earlier parser could not read (marginal notes set beside short body lines, section numbers printed apart from their text, several statutes in one Gazette issue). The second reader (pdftotext) checks each statute in its content-stream order and, where that order interleaves statutes or marginal notes on a shared page, in its physical reading order; every check is complete in the order that passes (each paragraph whole, nothing else in the statute's stretch but page furniture). The note on each version names the order used.
- 20-statutes-03: statutes an earlier parser could not read (marginal notes set beside short body lines, section numbers printed apart from their text, several statutes in one Gazette issue). The second reader (pdftotext) checks each statute in its content-stream order and, where that order interleaves statutes or marginal notes on a shared page, in its physical reading order; every check is complete in the order that passes (each paragraph whole, nothing else in the statute's stretch but page furniture). The note on each version names the order used.

## What AI did and did not do

The scripts that read the sources and build this repository were written by Claude Code running Claude Opus 5.5 (`claude-opus-5-5`) under Lexifina's direction.

No model wrote, translated or corrected legal text. No model runs at build time. Every word of law in this repository comes from the official sources above.

The commit messages are written by `build.py` from the source data.

Model use at data-build time:
- Claude Code (claude-opus-5-5) wrote Lexifina's code and chose the sources. No model output is used as legal text or dates: every word comes from the Gazette PDFs on the Council's website.
