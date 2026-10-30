# How this repository was made (Chad)

This file is written by the build on 2026-10-30, the day the source data was retrieved.

## Sources

| Source | Address | Retrieved | Licence |
| --- | --- | --- | --- |
| Présidence de la République du Tchad | <https://presidence.td/wp-content/uploads/2024/06/Constitution.pdf> | 2026-10-29 | Official legislation; no licence stated on presidence.td |
| FAOLEX (FAO): Code pénal 2017, loi n° 2017-01 du 8 mai 2017 [loi n° 001/PR/2017] | <https://faolex.fao.org/docs/pdf/cha213367.pdf> | 2026-10-30 | text of law republished by FAOLEX; no licence stated on the PDF |
| ILO NATLEX: Tchad, Loi no 38/PR/96 du 11 décembre 1996 portant Code du Travail (Internet Archive capture of 2 October 2017) | <https://www.ilo.org/dyn/natlex/docs/WEBTEXT/47297/65070/F96TCD01.htm> | 2026-10-30 | text of law, not protected by copyright (Bangui Agreement, Annex VII, art. 6(i)); ILO NATLEX copy |

Every word of law in this repository comes from these sources. Lexifina reads them and records each act's dated versions, and the laws that made each change, in one corpus file. This repository is built from that file.

## What is in it

| Act | Title | Versions | Span |
| --- | --- | ---: | --- |
| `constitution` | Constitution de la République du Tchad (2023) | 1 | 2023-12-29 to 2023-12-29 |
| `code-penal` | Code pénal (loi n° 2017-01 du 8 mai 2017, dite loi n° 001/PR/2017 portant Code pénal) | 1 | 2017-05-08 to 2017-05-08 |
| `code-du-travail` | Code du travail (loi n° 038/PR/96 du 11 décembre 1996) | 1 | 1996-12-11 to 1996-12-11 |

The build made 3 commits:

| Commits | Kind |
| ---: | --- |
| 3 | first version of an act |
| 0 | one law on its in-force day |
| 0 | changes no amendment note explains, credited to the publisher |

Other counts:
- 0 commits on the branch `futur`: laws not yet in force on 2026-10-30.
- 0 commits dated 1 January 1970: in force before 1970, with the real day in their `In-force` trailer.
- 1 laws in the record.
- 4 tags.

## Dates

Each commit is dated at noon (Africa/Ndjamena) on the day the change took effect. The other dates, enacted and published, are trailers.

When a law gives no date of its own, the default rule applies: Constitution du 29 décembre 2023, art. 283: « Elle entre en vigueur dès sa promulgation par le Président de la République ». It was promulgated on 29 December 2023 (Présidence, 29 décembre 2023). https://presidence.td/5eme-republique-la-constitution-promulguee-par-le-chef-de-letat/20430/

## How the history is built

`tools/build.py` turns the corpus into this history in one pass: one commit per law, on the day it took effect. The same corpus always gives the same commit hashes. `tools/check_repo.py` reads every version back from git and compares it with the corpus. `tools/on.py` shows the law as it stood on any date. The corpus format is described in `tools/SCHEMA.md`.

- Corpus: sha256 `6df9a1589bcb7873a937cbe92f8a8ef25c9b5597a3b83b52584aa5368ae5875b` (796466 bytes).
- Builder blob hashes (`git hash-object`): `build.py` `a4faa25af85facb64b956b372f6b528aafdd7ec1`, `check.py` `3d00541d258745461ab52b1b0cb4e1716a27a95d`, `on.py` `644a6c0857fbcc72562032b58d57aa113fee0641`.
- Python 3.12.10; git version 2.46.0.windows.1.

## Checks

3 versions of 3 acts read back from git on the day each took effect and on the day before: 0 mismatches. Trailers: 0 commits whose trailers git cannot parse. Health: 0 merge commits on main, 0 commit dates that go backwards, 0 commits dated after the build.

A second build from the same corpus into an empty folder gave identical hashes for all 3 history commits and 4 tags (history tip `aaa494b5cbc717a3b8494836c31fa7607fad0052`).

## Decisions made by hand

- The Constitution is dated by its promulgation, 29 December 2023, as art. 283 makes it take effect on promulgation; the referendum was held on 16-17 December 2023.
- Only the 2023 text is recorded: the Présidence reports a technical revision (loi constitutionnelle du 3 octobre 2025, promulgated 8 October 2025), but no text of the revised Constitution was found, so it is not recorded.
- Arts. 283 to 290 are printed together in one line in the PDF and were split at each "Article N :"; titles and chapters are kept as their own files; page numbers and the table of contents were removed. Art. 134 is misprinted "134l" in the PDF and is read as 134.
- Code pénal: one version, the Code as enacted (first_law null, oldest version available), dated 2017-05-08, the date of the law; its article 523 only orders publication in the Journal officiel, and sources differ on when it took effect, so the law date is used. Later amendments are not applied.
- Code pénal units: one per article (art-001 to art-523); the PDF has no articles 64, 148, 294 or 359, so those units do not exist; Livre, Titre, Chapitre and Section headings are left out; paragraph breaks are rebuilt from the PDF line layout.
- Code du travail: one version, the Code as enacted (first_law null, oldest version available), dated 1996-12-11, the date of loi n° 038/PR/96; its article 509 only orders publication in the Journal officiel, so the law date is used. Later amendments are not applied; a revised code adopted in draft by the Council of Ministers in September 2026 is not in force in this record.
- Code du travail units: one per article (art-001 to art-509); paragraphs and list items follow the HTML paragraphs of the NATLEX text; Livre, Titre, Chapitre and Section headings and the table of contents are left out.

## What AI did and did not do

The scripts that read the sources and build this repository were written by Claude Code running Claude Opus 5.5 (`claude-opus-5-5`) under Lexifina's direction.

No model wrote, translated or corrected legal text. No model runs at build time. Every word of law in this repository comes from the official sources above.

The commit messages are written by `build.py` from the source data.

Model use at data-build time:
- none
- Claude Code wrote the code and chose the source; it did not write or alter any legal text. The code is deterministic and runs no model.
- Claude Code wrote the code and chose the source; it did not write or alter any legal text. The code is deterministic and runs no model.
