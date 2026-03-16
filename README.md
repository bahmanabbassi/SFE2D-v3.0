# SFE2D (Full Version)

**Full version** of SFE2D: the complete 2D tool for **spatial and spectral feature extraction** from geo-images (PCA, ICA, CWT, S-PCA, S-ICA). This software is distributed as **P-codes** (`.p` files) with **SFE2D.fig**. No source `.m` files are included in this repository. Use is **license-controlled** and tied to your machine (MAC-based licensing).

**Lead Developer:** Bahman Abbassi  
**Principal Investigator:** Li-Zhen Cheng  
**Affiliation:** Institut de Recherche en Mines et en Environnement (IRME), Université du Québec en Abitibi-Témiscamingue (UQAT)

---

## What this version includes

- **Full feature set** with no demo limits:
  - **Multiple inputs:** Multiple satellite images and multiple XYZ (point) datasets.
  - **Full grid size:** No pixel limit; set spacing and grid dimensions as needed for your area.
  - **Spatial extraction:** PCA, kICA, nICA with full convergence and iteration controls.
  - **Spectral extraction:** All supported mother wavelets (Gaussian, Mexican Hat, Morlet, Cauchy, Paul, and others); full scale and angle ranges; adjustable CWT filter and scale dilation; S-PCA, S-kICA, S-nICA on CWT coefficients.
  - **Segmentation:** K-means with unrestricted number of colors; color-pick ROI tool.
  - **Export:** Surfer grids (`.grd`) and XYZ CSV.

- **MAC-based (machine) licensing:** Use is tied to the computer (MAC/hardware identifier). A valid license file (`SFE2D_license.lic`) must be present in the application directory to run the full version.

---

## Requirements

- **MATLAB:** R2021a (9.10) or later; tested up to R2025b.
- **Toolbox:** Wavelet Toolbox (for 2D CWT).
- **System:** Windows 7/8/10; ≥ 8 GB RAM recommended. Mac/Linux are not officially supported (use at your own risk if running under compatibility layers).

---

## Installation & run

1. Clone or download this repository.
2. Add the folder containing the **P-codes** (`.p` files) and **SFE2D.fig** to your MATLAB path, or set it as the current directory.
3. Ensure **SFE2D.fig** is in the same folder as **SFE2D.p**.
4. Place your **license file** (`SFE2D_license.lic`) in this same folder (see *Licensing & contact* below).
5. In the MATLAB Command Window:
   ```matlab
   SFE2D
   ```
   A valid MAC-based license is required; if none is found, the application will display instructions and your machine’s MAC address for obtaining a license.

---

## Workflow (short)

1. **Preprocessing** — Set geographic bounds (Min/Max Lon/Lat or polygon from CSV), grid spacing, then load one or more **satellite images** and/or **XYZ (point) data** CSVs. Data are interpolated to a common grid with optional Gaussian smoothing.
2. **Spatial extraction** — Choose **Select Inputs** (Satellite / Point Data / All), then run **PCA**, **kICA**, and/or **nICA** to obtain spatially separated components.
3. **Spectral extraction** — Set **CWT Inputs** (Image / XYZ / All), scales, angles, and mother wavelet; run **CWT**, then optionally **S-PCA**, **S-kICA**, and/or **S-nICA** on the CWT coefficients.
4. **Plot & export** — Use **Plot Results** (grayscale, RGB, k-means segmentation, color-pick) and **Exporting** (Surfer grids, XYZ CSV).

---

## Repository contents

The full version is provided as **P-codes only** (no source `.m` in this repository):

- **SFE2D.p**, **SFE2D.fig** — Main GUI (P-code; full functionality, license-checked).
- **validate_license.p**, **get_local_mac.p**, **get_license_instructions.p** — License validation (P-code).
- **PCA.p**, **fastICA.p**, **fastICA_CWT.p**, **kmeans_fast_Color.p**, **fig.p**, **FilterB.p**, **grd_write.p**, **centerRows.p**, **whitenRows.p**, **PlaceThresholdBars.p** — Core routines (P-code).

---

## Licensing & contact

- **MAC-based licensing:** Use of the full version is tied to your machine (MAC address). You must have a valid `SFE2D_license.lic` file in the application directory. The software is **proprietary** and **license-controlled**.
- **How to obtain a license:**  
  - **Academic / research (free):** Email your MAC address (shown in the app via the **License** menu or at startup if unlicensed) and a brief description of your research to **bahman.abbassi@uqat.ca**. Citation of published work is required.  
  - **Commercial / industry:** Contact **Prof. Li-Zhen Cheng** at **li_zhen.cheng@uqat.ca** for commercial or trial licensing (terms set by UQAT).  
  For more information and a limited-parameter demo, see the [SFE2D-Demo repository](https://github.com/bahmanabbassi/SFE2D-Demo) (no license required).

**Copyright:** © B. Abbassi, 2021. All rights reserved. No part of this software or documentation may be reproduced or transmitted without written permission from the author.

---

## References

- Abbassi, B., Cheng, L.Z. **SFE2D: A Hybrid Tool for Spatial and Spectral Feature Extraction.** In: *Mining Technology*. IntechOpen, 2022. DOI: [10.5772/intechopen.101363](http://dx.doi.org/10.5772/intechopen.101363)
- Abbassi, B., Cheng, L-Z., 2020, **SFE2D : Un outil d'extraction de caractéristiques spectrales de géo-images.** Rapport pour le ministère de l'Énergie et des Ressources naturelles, Bureau de la connaissance géoscientifique du Québec. [Lien (SIGEOM)](https://sigeom.mines.gouv.qc.ca/signet/classes/I1103_index?l=f&type_reqt=U&entt=LG&mode=NOUVELLE&format=RESUME&alias_table_crit=EXADOC&mnen_crit=NUMR_RAPR&oper_crit=EGAL&valr_crit=MB%202020-11)
- Abbassi, B., and Cheng, L-Z., 2019, **Integrated feature extraction in high-dimensional geophysical imaging.** Présentation à Québec Mines + Énergie 2019. DOI: [10.13140/RG.2.2.36577.93286](https://doi.org/10.13140/RG.2.2.36577.93286)
- SFE2D User Manual (ver. 2.0), April 2021.

## Dependencies

* **Fast K-means Algorithm for clustering Color Image:** ankit dixit (2026). *Fast kmeans Algorithm Code*, MATLAB Central File Exchange. Retrieved March 16, 2026. [Link](https://www.mathworks.com/matlabcentral/fileexchange/44598-fast-kmeans-algorithm-code)
* **Fast-ICA and PCA:** Brian Moore (2026). *PCA and ICA Package*, MATLAB Central File Exchange. Consulté le 16 mars 2026. [Lien](https://www.mathworks.com/matlabcentral/fileexchange/38300-pca-and-ica-package)

---

A **Demo version** (limited parameters, no license required) is available at: [https://github.com/bahmanabbassi/SFE2D-Demo](https://github.com/bahmanabbassi/SFE2D-Demo).
