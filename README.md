# Startup-Ecosystem-Analysis

A reproducible analysis and presentation repository exploring startup ecosystems. This README explains the project purpose, repo layout, how to reproduce the analysis, and how to extend or present the results.

## Repository layout

- [LICENSE](LICENSE) — MIT license for this repository.
- [README.md](README.md) — this file.
- [cleaned dataset/](cleaned dataset/) — processed and cleaned data files used for analysis (CSV/Parquet/JSON). These are the canonical data artifacts that analysis scripts and dashboards use.
- [Dashboard/](Dashboard/) — interactive dashboards and notebooks used for visualization and exploration (e.g., Jupyter notebooks, Streamlit apps, or dashboard export files).
- [PPT/](PPT/) — presentation slides and assets summarizing findings.

Open these paths to inspect content:
- [c:\GIT\Startup-Ecosystem-Analysis\LICENSE](LICENSE)  
- [c:\GIT\Startup-Ecosystem-Analysis\README.md](README.md)  
- [c:\GIT\Startup-Ecosystem-Analysis\cleaned dataset/](cleaned dataset/)  
- [c:\GIT\Startup-Ecosystem-Analysis\Dashboard/](Dashboard/)  
- [c:\GIT\Startup-Ecosystem-Analysis\PPT/](PPT/)

## Project goal

Provide a data-driven investigation of startup ecosystems: sourcing and cleaning data, deriving KPIs (founding rates, funding distributions, sector trends, geographic hotspots), producing reproducible visualizations and an executive slide deck.

## Typical contents (what to expect inside folders)

- Cleaned Dataset/
  - processed CSV(s) or Parquet files such as cleaned_startups.csv — canonical inputs for analysis.
  - a README or data-dictionary describing columns (create if missing).
- Dashboard/
  - Jupyter notebooks (.ipynb) that run analyses and generate plots.
  - Dash/Streamlit/Voila app code for interactive exploration.
  - Exported static visualizations (PNG/SVG).
- PPT/
  - .pptx slide deck summarizing insights and recommendations.
  - Supporting images exported from Dashboard.

If any of the above items are missing, add a short manifest file in each folder describing expected or produced artifacts.

## Reproducing the analysis

1. Create a reproducible environment
   - Prefer virtualenv, conda, or pipenv. Example using venv:
     - python -m venv .venv
     - .venv\Scripts\activate (Windows) or source .venv/bin/activate (macOS/Linux)
   - Install dependencies (create a `requirements.txt` in repo root if missing). Typical packages:
     - pandas, numpy, matplotlib, seaborn, plotly, jupyterlab, scikit-learn, streamlit (as needed).

2. Inspect and validate canonical data
   - Open [cleaned dataset/](cleaned dataset/) and confirm file names and schema.
   - Add a small validation notebook in [Dashboard/](Dashboard/) to assert expected columns and row counts.

3. Run notebooks or dashboard
   - Jupyter:
     - jupyter lab
     - Open notebooks from [Dashboard/](Dashboard/)
   - Streamlit (if app present):
     - streamlit run Dashboard/app.py

4. Regenerate visualizations and slides
   - Re-run analysis notebooks to produce updated figures in [Dashboard/](Dashboard/).
   - Export figures and update [PPT/](PPT/) slides; consider automating slide generation using python-pptx.

## Suggested project files to add (if missing)

- requirements.txt — pinned Python dependencies.
- environment.yml — conda environment file (optional).
- data-dictionary.md — schema and column definitions for cleaned dataset files.
- src/ or analysis/ — modular analysis scripts, functions, and utilities (to avoid heavyweight notebooks).
- tests/ — basic unit tests for data validation and processing.

## Best Practices and Reproducibility

- Keep raw data separate from cleaned/processed data (this repo contains cleaned datasets).
- Make cleaning scripts deterministic and idempotent; store random seeds for any sampling.
- Record data provenance: source, extraction date, transformation steps.
- Version large data artifacts with checksums or use a data storage service (DVC, S3).

## Contribution

- Create issues describing proposed changes or bugs.
- Add reproducible steps for others to validate (data checks, expected notebook outputs).
- Follow the MIT [license](LICENSE).

## Contact & attribution

This project is licensed under the MIT License (see [LICENSE](LICENSE)). For questions or contributions, open an issue or submit a pull request.

## Next steps (recommended)

1. Add `requirements.txt` or `environment.yml`.
2. Add a data dictionary in [cleaned dataset/](cleaned dataset/) describing each file.
3. Modularize notebooks into scripts under `src/` for easier testing and reuse.
4. Add a CI step (GitHub Actions) to run basic data checks on push.
