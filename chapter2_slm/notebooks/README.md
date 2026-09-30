# Chapter 2 notebooks

Python notebooks used to process the bibliographic records and produce the Chapter 2 figures. They were developed and run in Google Colab.

| Notebook | Input | Output |
|---|---|---|
| `Bibtex_notebook.ipynb` | `../data/raw/` | `../data/cleaned/` (cleaned `.bib` files and cleaning logs), `../data/deduplicated_pool.xlsx` |
| `Charts.ipynb` | `../data/df_clean_tagged_updated.xlsx`, `../data/slm_screening_completed.xlsx` | `../figures/` |

## Bibtex_notebook.ipynb

- Parses the four database exports with a regex-based parser. `bibtexparser` is not used for parsing because it drops Scopus entries whose keys contain spaces (e.g. `Sai Charan2022`).
- Removes records without authors (proceedings volumes and front matter) and renames duplicate keys that belong to distinct papers.
- Writes one cleaned `.bib` file and one cleaning log per database.
- Removes duplicates across databases: exact DOI match first, then fuzzy title match (rapidfuzz, 92% threshold, same-year guard). Precedence when a record appears in several databases: ACM > IEEE > Scopus > Web of Science.

## Charts.ipynb

- Maps the extracted features to canonical taxonomy tags (algorithm, hardware family, data type, libraries, metrics, connectivity, domain, power).
- Produces the bibliometric figures (records by database and year, included studies by year, database coverage, country map), the distribution charts and the algorithm taxonomy figure.

## Running the notebooks

File paths point to Google Drive (`/content/drive/MyDrive/...`). To run from a clone of this repository, set the path variables to the corresponding folders under `../data/`.

Main packages: pandas, openpyxl, rapidfuzz, bibtexparser, plotly, kaleido 0.2.1 (static image export), matplotlib.
