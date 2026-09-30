# Chapter 2: Systematic Literature Mapping

Systematic Literature Mapping (SLM) of TinyML-based anomaly detection in Artificial Intelligence of Things (AIoT) environments.

This chapter is based on the published article listed below. The systematic review presented here has been updated and extended for the thesis, incorporating a larger corpus and revised taxonomy beyond what was reported in the original publication.

## Pipeline

| Stage | Records |
|---|---|
| Database search (IEEE Xplore 363, Scopus 352, ACM 330, Web of Science 173) | 1,218 |
| Non-study records removed (proceedings front matter, editorials, entries without authors) | 213 |
| Duplicates removed (DOI match and fuzzy title match) | 356 |
| Title and abstract screening | 649 |
| Full-text assessment | 128 |
| Included studies  | 94 |

The search covers title, abstract and keyword fields with no lower year bound and an upper bound of 20 July 2026.

## Folder structure

| Folder | Content |
|---|---|
| `notebooks/` | Bibliographic processing (cleaning, deduplication) and chart/taxonomy notebooks |
| `data/raw/` | Database exports |
| `data/cleaned/` | Cleaned `.bib` files and per-database cleaning logs |
| `data/` | Deduplicated pool, screening decisions, extracted features and tagged corpus |
| `figures/` | Figures reported in Chapter 2 |

## Related publication

Trilles, S., Hammad, S. S., Iskandaryan, D. (2024). Anomaly detection based on Artificial Intelligence of Things: A Systematic Literature Mapping. *Internet of Things*, 25, 101063. https://doi.org/10.1016/j.iot.2024.101063
