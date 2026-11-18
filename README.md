# Mapping the water flow speed and warning time latency during flashflood of Trishuli River in Rasuwa Nepal
This project investigates the hydro-meteorological dynamics, institutional early-warning latency, and downstream infrastructure damage of the August 26, 2026 flash flood along the ~191 km Bhote Koshi–Trishuli–Narayani river corridor in central Nepal. By integrating river telemetry timestamps, satellite-derived damage grading, and building-level spatial footprints in R, this analysis evaluates how rapid-onset Himalayan flood waves outpace warning dissemination and identifies critical exposure hotspots across upstream and downstream municipalities.
## Research question
How did flood wave propagation velocity compare against institutional early-warning dissemination latency during the August 26, 2026 Rasuwa flash flood and what was the resulting spatial distribution of building and transport infrastructure along the Bhote Koshi-Trishuli corridor?
## Data
|File| Description| Source|

|"raw_data/flood_affected_area.shp"| shapefile of the area affected by flood| HDX
|"raw_data/impact_npl_s1_k50_damage_screening_admin3_v3.csv"| total impact caused by flood in different area| HDX
|"raw_data/hotosm_npl_points_of_interest_osm_shp"|  Shapefile of the flood affected area| HDX
|"raw_data/hot_flood_npl_destroyed_features_osm_shp"| shapefile of the features destroyed by flood| HDX https://data.humdata.org/dataset/hot_flood_npl
|"raw_data/Bhotekoshi-Trishuli_Flood_Update_From_August_26_2026_to_October_3_2026"|official mass SMS dispatch timestamps|https://ndrrma.gov.np/mediafiles/publications/Bhotekoshi-Trishuli_Flood_Update_From_August_26_2026_to_October_3_2026.pdf
|"raw_data/CHWRR Report II"|Station-by-station flood arrival/gauge failure timestamps, river chainage distances (km), water levels, and official mass SMS dispatch timestamps| https://chwrr.gov.np/content/57/report-on-rasuwa-bhotekoshi-flood-incident-2083--assessment/
## Repository Structure
Rasuwa_flashfloood_analysis_2026/
├── README.md ← you are here
├── raw_data/ ← original data, never edited
│ ├── CHWRR Report II.csv
│ └── Trishuli_Flood_Update_From_August_26_2026_to_October_3_2026.csv
│ └── impact_npl_s1_k50_damage_screening_admin3_v3.csv
│ └── hotosm_npl_points_of_interest_osm_shp
│ └── hot_flood_npl_destroyed_features_osm_shp
  └──flood_affected_area.shp
├── clean_data/ ← output of 1_data_clean.ipynb
│ └── stream_temp_clean.csv
├── figures/ ← plots and tables (coming in later scripts)
└── scripts/ ← notebooks, numbered in the order they run
├── 0_project_setup.ipynb
└── 1_data_clean.ipynb
## How to run the code
All scripts are Google Colab notebooks written in R. Run them in number order:
1. `scripts/0_project_setup.ipynb` creates the project folder and subfolders in
Google Drive.
2. `scripts/1_data_clean.ipynb` reads both raw files, reshapes and joins them, and
writes `clean_data/Rasuwa_flashdlood_analysis_2026.csv`.
Each notebook mounts Google Drive with one Python cell (`drive.mount()`), then
switches to the R runtime. See the notes at the top of each notebook.
   ## status and next steps
   
