# Cleaned BibTeX files

Output of the cleaning step applied to the raw exports in `../raw/`. Records without authors (proceedings volumes and front matter) are removed, and duplicate BibTeX keys that belong to distinct papers are renamed with a letter suffix (e.g. `Mellit2025` → `Mellit2025a`). Each database has a log listing every removed and renamed entry.

| Database | Raw | Removed | Renamed keys | Cleaned | File | Log |
|---|---|---|---|---|---|---|
| ACM Digital Library | 330 | 184 | 0 | 146 | `acm_cleaned.bib` | `acm_cleaning_log.md` |
| IEEE Xplore | 363 | 0 | 0 | 363 | `ieee_cleaned.bib` | `ieee_cleaning_log.md` |
| Scopus | 352 | 21 | 15 | 331 | `scopus_cleaned.bib` | `scopus_cleaning_log.md` |
| Web of Science | 173 | 0 | 0 | 173 | `wos_cleaned.bib` | `wos_cleaning_log.md` |
| **Total** | **1,218** | **205** | **15** | **1,013** | | |

The deduplication notebook removes a further 8 non-study records before deduplication (ACM: 2 workshop summaries and 1 tutorial abstract; IEEE: 4 front matter or call-for-papers entries without authors and 1 guest editorial). This gives the 1,005 records reported in Chapter 2 (213 non-study records removed in total).
