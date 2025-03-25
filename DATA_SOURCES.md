# Create DATA_SOURCES.md
data_sources_content = """# 📦 Data Sources for Exelant Script Generator

This guide lists all the **datasets** and **APIs** recommended or required for the successful operation of the full suite of geospatial scripts in this platform. These sources power analyses related to zoning, land use, environmental equity, real estate, housing, and infrastructure. This list is grouped by category, along with suggested access methods and usage notes.

---

## 🏘️ Zoning & Land Use

| Source | Description | Access |
|--------|-------------|--------|
| Local/Municipal GIS Zoning Layers | Parcel-level zoning polygons and zoning code attributes | Local government GIS portals |
| Zoning Texts | Full zoning ordinance for parsing and NLP | PDF/HTML from planning department websites |
| Planning Proposals | Datasets on proposed zoning changes | Municipal planning boards |

---

## 📏 Parcels, Buildings, and Infrastructure

| Source | Description | Access |
|--------|-------------|--------|
| County Parcel Data | Property boundaries, use codes, FAR, assessed values | Local property appraiser or GIS open data |
| Building Footprints | Building outlines and heights | Microsoft Open Buildings, local GIS |
| Surface Parking | Derived from aerial imagery or land use codes | Satellite + local data |
| Infrastructure Layers | Roads, transit, sewer, etc. | Local or regional open data hubs |

---

## 🌍 Basemaps and Context Layers

| Source | Description | Access |
|--------|-------------|--------|
| OpenStreetMap | Streets, amenities, buildings, land use | OSM API or Geofabrik downloads |
| Census Boundaries | Tracts, block groups, PUMAs | U.S. Census TIGER/Line Shapefiles |

---

## 🧑‍🤝‍🧑 Demographic & Housing Data

| Source | Description | Access |
|--------|-------------|--------|
| American Community Survey (ACS) | Income, race, tenure, housing burden, etc. | [data.census.gov](https://data.census.gov) |
| PUMS | Microdata used for disaggregation | [Census PUMS](https://www.census.gov/programs-surveys/acs/microdata.html) |
| HUD CHAS | Housing need and affordability metrics | [HUD CHAS Data](https://www.huduser.gov/portal/datasets/cp.html) |

---

## 🌡️ Environment & Climate

| Source | Description | Access |
|--------|-------------|--------|
| NDVI/Tree Canopy | Vegetation health for heat island mapping | Google Earth Engine |
| LST (Land Surface Temp) | Urban heat mapping | NASA MODIS / Google Earth Engine |
| Flood Risk | FEMA Flood Zones | FEMA NFHL or MSC GIS Data Portal |
| Green Infrastructure | Parks, open space | Local GIS or Trust for Public Land |

---

## 💰 Real Estate & Market Data

| Source | Description | Access |
|--------|-------------|--------|
| Zillow ZORI/ZHVI | Rent and home value trends | [Zillow Research](https://www.zillow.com/research/data/) |
| CompStak / CoStar | Commercial lease and sale comps | Requires subscription |
| Permit Data | Construction or zoning permits | Municipal open APIs (e.g. NYC DOB, Miami) |

---

## 🧠 AI & ML Model Sources

| Source | Description | Access |
|--------|-------------|--------|
| Satellite Tiles | Image tiles for inference (e.g. tree cover, solar roofs) | Google Earth Engine, Google Cloud Storage |
| Pretrained ML Models | Vision models for detection tasks | Hugging Face, TensorFlow Hub, PyTorch Hub |

---

## 🧰 DevOps & Storage (Recommended for Logging & Versioning)

| Source | Description | Notes |
|--------|-------------|-------|
| Google Cloud Storage (GCS) | Store raw and processed files | Register via Google Cloud Console |
| Google BigQuery | Tabular data warehouse (optional) | Great for syncing ACS or Zillow |
| DuckDB | Embedded SQL for local runs | Installed locally |
| PostgreSQL/PostGIS | Spatial SQL backend for large projects | Cloud or Docker install |

---

## ✅ Registration Steps

1. **Google Cloud Platform** – Create a project, enable GCS, Earth Engine, and BigQuery.
2. **Census API Key** – Get one at [https://api.census.gov/data/key_signup.html](https://api.census.gov/data/key_signup.html)
3. **Zillow Terms** – Accept their terms to use bulk data
4. **FEMA GIS** – Use their FTP or Web Services
5. **OpenStreetMap** – No registration needed
6. **Local GIS Portals** – Look for open data license or request access

---

### 📂 Recommended Local Directory Structure

```
data/
├── parcels/
├── zoning/
├── buildings/
├── acs/
├── pums/
├── flood/
├── ndvi/
├── zillow/
├── permits/
└── raw_downloads/
```

---

This file complements `AGENTS_AND_UPGRADES.md` and the README to ensure all scripts have the data they need to function automatically.
"""

with open("DATA_SOURCES.md", "w") as f:
    f.write(data_sources_content)