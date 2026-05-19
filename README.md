# Automated SAR Flood Extent Extraction: 2022 Pakistan Monsoons

## Project Overview
This repository contains a cloud-based spatial analysis pipeline developed using the **Google Earth Engine (GEE) Python API**. The project maps and quantifies the severe inundation along the Indus River basin (Rajanpur District, Punjab) during the historic 2022 Pakistan monsoons.

By processing raw microwave backscatter data from satellite radar, this script bypasses heavy monsoon cloud cover to mathematically isolate standing floodwater from dry agricultural and residential zones.

**Core Finding & Extraction Metric:** The automated machine learning pipeline successfully isolated and quantified **422.88 sq km** of standing floodwater directly invading surrounding housing and agricultural plains.

## Technology & Data Stack
* **Cloud Computing:** Google Earth Engine API (Server-side spatial reductions)
* **Language:** Python
* **Data Asset:** Copernicus Sentinel-1 SAR (Synthetic Aperture Radar)
* **Parameters:** C-band, VV Polarization, Interferometric Wide (IW) swath mode
* **Visualization:** Folium (Interactive Web Maps), Matplotlib (Static Rendering)

## Scientific Methodology
Unlike optical satellites (which are blinded by clouds), SAR emits microwave pulses. 
* **Water (Black):** Calm floodwater acts as a specular reflector, bouncing the signal away from the sensor (low backscatter / 0).
* **Land/Infrastructure (Gray/White):** Rough terrain, crops, and buildings cause diffuse scattering, returning the signal to the sensor (high backscatter).

By applying targeted thresholding to these backscatter values, the algorithm accurately extracts the flooded areas.

## Visual Evidence: The Indus River Breach
*(Note: Replace these placeholder links with the actual links to your uploaded images)*

**Map 1: Pre-Monsoon Baseline (June 2022)**
![Pre-Flood Baseline](https://earthengine.googleapis.com/v1/projects/flood-extent-mapping-punjab/thumbnails/eb1715ec1eb4cc8ec7742a2b32fadbf5-473d8744d6d83cac0b03d0af326b2b6b:getPixels)
*The narrow, standard flow of the Indus River prior to the monsoon.*

**Map 2: Peak Inundation Extent (Late Aug / Sept 2022)**
![Peak Flood](https://earthengine.googleapis.com/v1/projects/flood-extent-mapping-punjab/thumbnails/e6617f37b5f8731f069e683223c23ec3-66019f7e9979e1741d35bb722c0da77b:getPixels)
*Massive signal absorption (black voids) indicating widespread flooding over agricultural and housing zones.*

## How to Run the Pipeline
This code is designed to run entirely in the cloud via Google Colab, requiring no local GIS software installation.
1. Open the `.ipynb` notebook.
2. Run the first cell to authenticate your Google Earth Engine account.
3. Execute the pipeline to generate the spatial matrices and stream the remote sensing tiles directly to the output console.
