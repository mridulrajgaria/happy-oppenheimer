# HAPPY OPENHEIMER

A private, browser-based matcher for identifiers and names. It runs as a static GitHub Pages site; no application server or shared database is used.

## Features

- Paste IDs or extract them from XLSX, XLS, CSV, PDF, DOCX, and TXT files.
- Import a CSV or Excel master list containing an ID column and a Name column.
- Update matching records, retain other records, and save the master list in this browser.
- Copy matching results or download them as an Excel workbook.

## Privacy and storage

The master list is stored in the current browser's local storage and is not shared with other users or devices. Uploaded files are processed in the browser. The repository intentionally excludes `master_list.csv` and `neo_master.db`, which may contain personal records.

The spreadsheet, PDF, and DOCX parsing libraries are loaded from public CDNs. File contents and saved records are not sent to those services.

Clearing browser site data will remove the locally saved master list. Use **Clear this device’s master list** in the app to remove it explicitly.

## GitHub Pages deployment

The workflow in `.github/workflows/pages.yml` deploys `index.html` whenever code is pushed to `main`, or when started manually from GitHub Actions. In the repository settings, set **Pages → Build and deployment → Source** to **GitHub Actions**.

## Local Python version

The original Streamlit version remains available locally:

```powershell
python -m pip install -r requirements.txt
python -m streamlit run app.py
```

Keep its local database or master list outside public commits.
