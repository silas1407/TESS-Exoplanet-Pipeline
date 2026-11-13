# NASA TESS Exoplanet Transit Detection Pipeline

An automated data science pipeline in Python to query, clean, and analyze high-cadence space telescope photometry from NASA's Transiting Exoplanet Survey Satellite (TESS).

---

## What It Does
Raw space telescope data contains massive instrumental noise, scattered light, and stellar variability. This pipeline automates the process of pulling Target Pixel Files (TPFs) from NASA's MAST archive, detrending the light curves, and running Box Least Squares (BLS) periodogram analysis to detect periodic flux dips caused by exoplanet transits.

## Pipeline Workflow
1. **Data Ingestion:** Queries the Mikulski Archive for Space Telescopes (MAST) using `lightkurve` to download FITS light curve files for target stars.
2. **Systematic Detrending:** Applies sliding-window median filters and flat-field corrections to strip out instrumental jitter and stellar flare noise.
3. **Periodogram Analysis:** Runs BLS across temporal frequency spectra to identify periodic flux drops matching the planet-to-star radius ratio relation:
    Fractional Flux Drop: (ΔF / F) ≈ (Rp / R_*)²

## Tech Stack
* Python 3.x
* `lightkurve`, `astropy` (NASA MAST API)
* `numpy`, `scipy`, `pandas` (Time-series signal processing)
* `matplotlib` (Phase-folded transit light curve plotting)

## Running Locally
```bash
git clone [https://github.com/silas1407/TESS-Exoplanet-Pipeline.git](https://github.com/silas1407/TESS-Exoplanet-Pipeline.git)
cd TESS-Exoplanet-Pipeline
pip install lightkurve astropy matplotlib scipy numpy pandas
python tess_pipeline.py
