# AMERTA — MCDA for Retention Ponds Site Suitability (QGIS Plugin)

A QGIS plugin to identify and prioritize potential **retention ponds** locations using **Multi-Criteria Decision Analysis (MCDA)**.

<p>
  <strong>QGIS:</strong> ≥ 3.40 (LTR OK) •
  <strong>OS:</strong> Windows / Linux / macOS •
  <strong>License:</strong> GPL-3.0+
</p>

## Features
- **Rainfall analytics (CHIRPS):** annual sum/mean and PCA-based variability (eigenvector).
- **Gridded factors:** per-cell rainfall, TWI, Soil Type (JTNH), Land Cover (PL).
- **MCDA scoring & combine:** computes `S_Rain`, `S_TWI`, `S_PL`, `S_JTNH`, and overall suitability.
- **Utilities:** class standardization, AOI clipping, reproducible outputs.

## Installation
**A) From release ZIP (recommended)**
1. Download the latest `.zip` from **Releases**.  
2. QGIS → *Plugins* → *Manage and Install…* → *Install from ZIP* → choose the file.

**B) From source**
```bash
git clone https://github.com/sitasatu/AMERTA.git
# Copy the 'AMERTA' folder into your QGIS plugins directory:
# Windows: %AppData%\QGIS\QGIS3\profiles\default\python\plugins\
# Linux:   ~/.local/share/QGIS/QGIS3/profiles/default/python/plugins/
# macOS:   ~/Library/Application Support/QGIS/QGIS3/profiles/default/python/plugins/
# Restart QGIS, then enable the plugin (Plugins → Manage and Install…)
```

## Quickstart
1. Enable the plugin (Plugins → Manage and Install… → search “**AMERTA**”). 
2. Open Processing Toolbox → **AMERTA** group.

## Typical flow
Inputs: AOI polygon; rasters (CHIRPS annual rainfall mm/yr, PCA eigenvector PC1, TWI); vectors (standardized JTNH & PL).

1. Prepare rainfall: CHIRPS – Annual (Sum) / PCA Variability.
2. Prepare topographic wetness index (TWI)
3. Map source fields to standardized Land Cover and Soil Type classes.
4. Build grids & factors: Grid Rainfall, Grid TWI, Grid Soil Type (JTNH), Grid Land Cover (PL).
5. Combine factors with MCDA → overall suitability (e.g., MCDA).

Output: a grid layer with factor fields and suitability class for retention ponds siting.

## Reporting Issues / Contributing
- Open an Issue with QGIS version, OS, steps to reproduce, and logs/screenshots.
- PRs welcome—keep folder structure consistent and, when possible, include tiny test data.

## Citation
If you use AMERTA in publications, please cite (APA 7th):
<p>Safitri, S., Roswintiarti, O., Saputra, O. F., Chulafak, G. A., Nugroho, G., Sunarmodo, W., Sukowati, K. A. D., & Fitriana, H. L. (2025). AMERTA: A QGIS plugin for MCDA-based retention ponds siting (v1.0.2) [Computer software]. Badan Riset dan Inovasi Nasional (BRIN). https://github.com/sitasatu/AMERTA</p>

## License & Credits
Released under GNU GPL-3.0 or later. See LICENSE.
<p><strong>Authors</strong>: Sitarani Safitri, Orbita Roswintiarti, Okta Fajar Saputra, Galdita Aruba Chulafak, Gatot Nugroho, Wismu Sunarmodo, Kusumaning Ayu Dyah Sukowati, Hana Listi Fitriana (see metadata.txt).</p>

<p><strong>Acknowledgments</strong>: CHIRPS rainfall, DEM sources, and collaborators.
