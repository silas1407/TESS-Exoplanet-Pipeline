# 🌌 AstroData: Automated TESS Exoplanet Discovery & 3D Blender Pipeline

An open-source, end-to-end research tool designed for astronomers, researchers, and students to automatically query space telescope data, compute exoplanet parameters, invert planetary masses via N-body simulations, and procedurally render 3D star systems in Blender.

---

## 🚀 Features
- **Light Curve Processing:** Pulls photometric data directly from the NASA MAST archive (`Lightkurve`)[cite: 1].
- **Periodogram Scanning:** Uses Box Least Squares (BLS) to detect exoplanet orbital periods and transit depths[cite: 1].
- **N-Body Mass Inversion:** Simulates gravitational interactions using `REBOUND` to calculate Transit Timing Variations (TTVs) and infer planetary masses[cite: 1].
- **Procedural 3D Generation:** Automatically streams parameters via JSON into a Python script in Blender to generate starfield backgrounds, turbulent host stars, orbital paths, and multi-planet systems.

---

## 🛠️ Tech Stack
- **Python** (Google Colab backend)
- **Astropy / Lightkurve / REBOUND** (Astrophysics & N-body dynamics)
- **Blender (Python API / Eevee Engine)** (3D procedural visualization)

---

## 🏃‍♂️ Quickstart Guide

### Step 1: Run the Colab Backend
1. Open the notebook in [Google Colab](https://colab.research.google.com/drive/1wFFB4-Gl5_4k6tHq5yBrBwaHGqpp3i2_#notebook-main)[cite: 1].
2. Press Run all
3. Enter your target star name (e.g., `Kepler-11`, `TRAPPIST-1`)[cite: 3].(as of right now it is set to WASP-47 ,but, you can enter any star you wish)
5. Run through the pipeline cells to process light curves[cite: 1] and export the system parameters JSON file.

### Step 2: Render in Blender
1. Open Blender and go to the **Scripting** tab.
2. Load the `exoplanet_universal_renderer.py` script.
3. Update the `json_filepath` variable to point to your downloaded system JSON file.
4. Hit **Run Script** to instantly generate the star system!
