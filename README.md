# HAPPY OPENHEIMER

A browser-based matcher for identifiers and names. It runs as a static GitHub Pages site; no application server or shared database is used.

## Features

- Paste IDs or extract them from XLSX, XLS, CSV, PDF, DOCX, and TXT files.
- Automatically load the published `master_list.csv` on each visit.
- Import a CSV or Excel master list containing an ID column and a Name column.
- Save the loaded and imported master list in this browser for later visits.
- Copy matching results or download them as an Excel workbook.

## Privacy and storage

**The published `master_list.csv` is public. Its IDs and names are included in this GitHub repository and in the public site download.** The site loads that list on each visit and saves a copy in the current browser's local storage. Imported changes are local to that browser; on the next visit, the published list refreshes those IDs that appear in the CSV.

Uploaded files are processed in the browser. The spreadsheet, PDF, and DOCX parsing libraries are loaded from public CDNs; file contents and saved records are not sent to those services. `neo_master.db` remains excluded from GitHub.

Clearing browser site data removes the locally saved copy; the list will be loaded again from the public CSV on the next visit.

## GitHub Pages deployment

The workflow in `.github/workflows/pages.yml` deploys `index.html` whenever code is pushed to `main`, or when started manually from GitHub Actions. In the repository settings, set **Pages → Build and deployment → Source** to **GitHub Actions**.

## Local Python version

The original Streamlit version remains available locally:

```powershell
python -m pip install -r requirements.txt
python -m streamlit run app.py
```

The local database remains excluded from public commits. The master CSV is intentionally public so GitHub Pages can load it automatically.
