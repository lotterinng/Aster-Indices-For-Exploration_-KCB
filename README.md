# Aster-Indices-For-Exploration_-KCB
This repository contains the complete workflow for mapping mineral alteration indices using ASTER satellite imagery over the Kalahari Copperbelt, a globally significant frontier for sediment-hosted copper exploration.

ASTER Mineral Indices Mapping for Copper Alteration Zones
A Study of the Kalahari Copperbelt (Sediment-Hosted Copper Exploration)
📚 Project Overview
This project leverages ASTER (Advanced Spaceborne Thermal Emission and Reflection Radiometer) satellite imagery to systematically generate mineral indices for the Kalahari Copperbelt, a major emerging frontier for sediment-hosted copper (Cu) exploration.
Through the combination of Earth Engine cloud processing and raster-based spatial analysis, mineral alteration proxies indicative of copper mineralization (e.g., iron oxides, carbonates, clays, laterites) are derived, exported, and visualized.

The outputs include georeferenced mineral index rasters and thematic alteration maps that can inform exploration targeting, mineral system modeling, and prospectivity analysis.

🧩 Methodological Pipeline

Stage	Description
1. Environment Setup	Installation of geospatial libraries: Earth Engine API, geemap, geopandas, rasterio, matplotlib
2. ROI Specification	The Region of Interest (ROI) is the Kalahari Copperbelt, uploaded as an Earth Engine asset
3. Image Collection Filtering	ASTER L1T scenes between 2000–2020, with <5% cloud cover, intersecting the ROI
4. Index Computation	Mineral indices calculated via spectral band ratios and algebraic combinations for specific mineral groups
5. Raster Export	Export of median composites of indices as GeoTIFFs clipped to the ROI at 500m scale
6. Post-processing	Raster masking, plotting, visualization enhancements (north arrow, colorbars, extent controls)
🧪 Mineral Indices and Geological Rationale

Mineral Group	Band Ratio Expression	Geological Target

Ferric Iron (Fe³⁺) B2 / B1	Oxidized iron cap (gossans), key indicator of Cu-Fe oxides
Ferrous Iron (Fe²⁺)	(B5/B3N) + (B1/B2)	Reduction zones, alteration halos around copper
Laterite	B4 / B5	Weathering surfaces, supergene copper enrichment
Carbonates / Mafics	(B7 + B9) / B8	Host rocks, mineralized structures
Sericite/Illite/Smectite	(B5 + B7) / B6	Hydrothermal clay alteration around Cu systems
Alunite/Kaolinite/Pyrophyllite	(B4 + B6) / B5	Advanced argillic alteration, acidic fluids linked to mineralization
Phengitic Muscovite	B5 / B6	Stable phyllosilicates in structural traps
Silica / Quartz Zones	B14 / B12, B13 / B10	Silicified structures, brittle conduits for fluid flow
Alteration Zones	B4 / B5	General indicator of hydrothermal alteration intensity
Host Rock Analysis	B5 / B6	Baseline mineralogy for comparative studies

🗺️ Outputs
GeoTIFF Raster Layers for each mineral index:

AsterMineralIndexFI.tif — Ferric Iron

AsterMineralIndexF2.tif — Ferrous Iron

AsterMineralIndexL.tif — Laterite

AsterMineralIndexCCE.tif — Carbonates / Mafics

AsterMineralIndexSMIS.tif — Silicates

AsterMineralIndexAKP.tif — Alunite/Kaolinite/Pyrophyllite

AsterMineralIndexPh.tif — Phengitic Muscovite

AsterMineralIndexAL.tif — Alteration Zones

AsterMineralIndexHR.tif — Host Rocks

AsterMineralIndexQ.tif — Quartz Zones

AsterMineralIndexSI.tif — Silica Zones

Map Visualizations (high-quality PNG figures):

Thematic maps styled with matplotlib, including scale bars, north arrows, legends, and mineral-specific color ramps.

🚀 How to Reproduce
Install Required Packages:
bash
Copy
Edit
pip install earthengine-api geemap rasterio geopandas matplotlib
Authenticate Earth Engine:
python
Copy
Edit
import ee
ee.Authenticate()
ee.Initialize(project='your-project-id')
Execute the Scripts:
Each section (iron oxides, laterites, clays, etc.) follows the pattern:

Filter ImageCollection

Apply mineralogical band ratio

Clip to ROI

Export Raster

Visualize masked output

📍 Study Area Context
Region: Kalahari Copperbelt, Botswana–Namibia

Geological Setting:
The Kalahari Copperbelt hosts sedimentary basin red-bed deposits — typically featuring copper sulfide mineralization controlled by lithological contacts and structures.
The application of ASTER-based remote sensing aims to identify:

Oxidized zones (gossans)

Hydrothermal alteration patterns

Host lithologies

This project supports pre-drilling exploration strategies by refining prospectivity zones through non-invasive spectral methods.
