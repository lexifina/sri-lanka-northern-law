# Northern Province (Sri Lanka): law history in git

Part of [lexifina/global-law](https://github.com/lexifina/global-law), one git history for every country's law: this is the law of Northern, Sri Lanka, which global-law reads at `sri-lanka/northern/acts/`.

The statutes of the Northern Provincial Council, Sri Lanka, as a git history: one folder per statute, one paragraph per line, so `git blame`, `git log` and `git diff` work line by line. The text is the English text of each statute as published in the Gazette of the Democratic Socialist Republic of Sri Lanka (Extraordinary), Part IV (A), Provincial Councils, and posted by the Northern Provincial Council on its website.

It follows the shared design of [lexifina/global-law](https://github.com/lexifina/global-law).

## What this repository holds

**Statutes as published, not yet a history.** The Council posts each statute as the Gazette Extraordinary that published it; there is no consolidated text. So each statute is one commit holding its text as published ("oldest version available"), credited to the Council, not to an amending law. An amending statute is its own folder; its amendments are not applied to the statute it amends.

| Folder | What |
| --- | --- |
| one folder per statute (by the short title it gives itself) | one file per section (`000-title.md` for the heading, long title and enacting words), or one file `000-text.md` with the whole statute where its sections cannot be told apart reliably |

Statutes are enacted in Sinhala and Tamil as well; this repository holds the English text only. Where a statute says which language prevails, it says so in its own words here. A statute is left out until it can be read reliably (see "Limits"); this record holds only part of the Northern Provincial Council's statutes.

## Source

[Northern Provincial Council: statutes](https://np.gov.lk/statutes/), each a PDF of the Gazette Extraordinary (Part IV (A)) with a text layer. Each PDF's sha256 is recorded with its version in `data/versions.json`.

## Dates

The four statutes added in the November 2026 batch are dated by the Governor assent explicitly recorded in the Council publication notice, following section 1. Gazette publication dates are recorded separately. Earlier records retain their original Gazette-date convention and await a commencement-date audit.

## How it is built

Lexifina reads the sources listed here and records each act's dated versions, and the laws that made each change, in one corpus file. `tools/build.py` writes this repository from that file, and the same corpus always gives the same commit hashes; `REPRODUCE.md` gives the details and the checks. A model (Claude) wrote Lexifina's code; it wrote no legal text, and no model runs when the history is built.

The text layer of each PDF (no OCR) becomes the record. Left out: the Gazette masthead, running heads and the Sinhala/Tamil lines in legacy fonts, page labels, printing footers, the Council Secretary's publication notice, and marginal notes where the statute is kept as one file. Where sections are split, each section file gives its marginal note on the line before the section text.

## How it is checked

Every version is read back from git on the day it took effect and must match the corpus. A second, independent reading of every PDF (pdftotext for the earlier records; pypdf for the November 2026 additions) must contain every paragraph of each statute whole, letter for letter and digit for digit, with nothing in the statute's stretch of the Gazette left out. Results are in `REPRODUCE.md`.

## What "author" means

The author of each commit is the publisher, with an e-mail address that cannot exist; the committer is always Lexifina.

## Limits

Only the English statutes as published are here. Amending statutes have their own records; their changes are not applied to their principal statutes. This record has no consolidated current texts and includes only statutes that pass the text checks. The Gazette is authoritative.

## Licence

See [LICENSE](LICENSE): official texts of a legislative nature are not protected by copyright under the Intellectual Property Act, No. 36 of 2003, section 8. Source: Northern Provincial Council; Gazette of the Democratic Socialist Republic of Sri Lanka (Department of Government Printing).

## November 2026 additions

| Statute | In force | Gazette published |
| --- | --- | --- |
| Northern Province Child Day Care Centre Statute No. 03 of 2016 | 2016-10-28 | 2016-11-02 |
| Northern Province Child Development Centre Statute No. 04 of 2016 | 2016-11-21 | 2016-11-25 |
| Northern Province Health Services (Amendment) Statute No. 10 of 2016 | 2017-07-11 | 2017-07-14 |
| Finance (Amendment) Statute of Northern Province No. 04 of 2017 | 2017-10-13 | 2017-10-24 |

These additions include the Child Day Care Centre and Child Development Centre statutes and separate Health Services and Finance amending statutes. The amendments are not applied to their principal statutes in this record.
