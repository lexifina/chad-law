# Chad: law history in git

The law of Chad as a git history. Each provision is one file, each law gets one commit on the day it took effect, and the law that made each change is the commit's author. `git blame` names the law behind every paragraph and `git log` lists every change to an article.

It follows the shared design of [lexifina/global-law](https://github.com/lexifina/global-law), which places it at `td/`.

This is an early build: the Constitution of 2023 as promulgated, and the statutes listed below.

## What is in it now

| Folder | Act | Versions | History |
| --- | --- | ---: | --- |
| `constitution/` | Constitution de la République du Tchad (2023), 290 articles | 1 | As promulgated, in force 29 December 2023; the technical revision of October 2025 is not in the record |
| `code-penal/` | Code pénal (loi n° 2017-01 du 8 mai 2017) | 1 | Oldest version available: the Code as enacted, dated 8 May 2017, with no later amendments (519 articles; the PDF has no articles 64, 148, 294 and 359) |
| `code-du-travail/` | Code du travail (loi n° 038/PR/96 du 11 décembre 1996) | 1 | Oldest version available: the Code as enacted, dated 11 December 1996, with no later amendments (509 articles) |

## Where the text comes from

The text is the Constitution of the Republic of Chad, approved by referendum on 17 December 2023, as published by the Présidence de la République du Tchad (presidence.td) as a PDF in June 2024, retrieved on 29 October 2026. The Présidence's news item of 29 December 2023 records the promulgation. The Journal officiel numérique (journalofficiel.td) is the official gazette, but its texts are not readable from a plain page.

Language: French, one of the two official languages (art. 10); the Arabic text is not in this record.

## Not included yet

- The technical revision of the Constitution (loi constitutionnelle du 3 octobre 2025, promulgated on 8 October 2025). The Présidence reports it, but no text of the revised Constitution was found, so the current Constitution may differ from this record.
- The Arabic text.
- Every other law of Chad, apart from the statutes listed above.

## Code pénal

The Code pénal is the text as enacted on 8 May 2017 (loi n° 2017-01, also cited as n° 001/PR/2017), from the FAOLEX copy of a droit-afrique.com PDF. It is dated by the law, since sources differ on when it took effect. Headings are left out and paragraph breaks are rebuilt from the PDF line layout.

## Code du travail

The Code du travail is the text as enacted on 11 December 1996 (loi n° 038/PR/96), from the text held in the ILO's NATLEX database (read from an Internet Archive copy of 2 October 2017). It is dated by the law, since the law only orders its publication. Headings are left out; paragraphs and list items follow the NATLEX text.

## Dates

The version is dated 29 December 2023, the day the Constitution was promulgated; art. 283 makes it take effect on promulgation. The vote was held on 16 and 17 December 2023. The commit is dated noon, Africa/Ndjamena, on that day and is credited to the Constitution itself.

## How it is checked

Every version is read back from git on the day it took effect and on the day before; both must match the corpus the repository was built from. The results are in `REPRODUCE.md`.

## How it is built

Lexifina reads the sources listed here and records each act's dated versions, and the laws that made each change, in one corpus file. `tools/build.py` writes this repository from that file, and the same corpus always gives the same commit hashes; `REPRODUCE.md` gives the details and the checks. A model (Claude) wrote Lexifina's code; it wrote no legal text, and no model runs when the history is built.

Lexifina reads the sources listed here and records each act's dated versions, and the laws that made each change, in one corpus file.

## What "author" means

The author of a commit is the law that made the change. Its e-mail address cannot exist, so `git blame` and `git log --author` name laws. A version with no law of its own (the oldest version available) is authored by the publisher and says so. The committer is always Lexifina.
