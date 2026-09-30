# Chapter 2 data

| Stage | Folder / file | Records |
|---|---|---|
| Search exports | `raw/` | 1,218 |
| Cleaned exports | `cleaned/` | 1,013 |
| Deduplicated pool | `deduplicated_pool.xlsx` | 649 |
| Screening and data extraction | `slm_screening_completed.xlsx` | 94 included |
| Tagged corpus | `df_clean_tagged_updated.xlsx` | 94 |
| Author affiliations | `slm_author_affiliations.xlsx` | 94 |

## Files

**`deduplicated_pool.xlsx`**: pool after removing 8 further non-study records (1,005) and 356 duplicates (349 exact DOI matches, 7 fuzzy title matches at a 92% threshold with a same-year guard). When a record appears in several databases, the kept copy follows the precedence ACM > IEEE > Scopus > Web of Science.

**`slm_screening_completed.xlsx`**: extracted features of the 94 included studies, one row per study, keyed by `gid`. Fields: Hardware, Hardware category, Data type, Algorithm, Metrics, Connectivity, Libraries, Power, Memory, Realtime, Dataset, Architecture, Security, Privacy, Domain, UseCase, Performance, Training, Inference, Energy, Comments.

**`df_clean_tagged_updated.xlsx`**: the same 94 studies with canonical taxonomy tags used for the Chapter 2 figures: `algorithm_tags`, `hardware_family_tags`, `datatype_domain_tags`, `library_tags`, `metric_tags`, `connectivity_tags`, `domain_tag`, plus `is_seed` flagging the 18 studies of the published mapping.

**`slm_author_affiliations.xlsx`**: author affiliations and countries of the 94 studies (sheets: studies, affiliations, countries). The country of each study is the country of the first-listed affiliation.

