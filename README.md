# mesopelagic_squid_okuyama_2026
Supplementary materials for submitted article for Okuyama et al 2026

## Introduction
The diamond squid (*Thysanoteuthis rhombus*, also called **sodeika**) is a large cephalopod inhabiting subtropical and tropical waters of the Pacific. It is capable of fast swimming speeds (up to ~5 km/h) and exhibits strong diel vertical migrations between surface and deep layers.

This project uses **biologging tags (MiniPAT, Wildlife Computers)** to collect depth, temperature, and light data. These observations are integrated with ocean model outputs and processed through the **PANGEO-FISH** software to reconstruct squid migration pathways and vertical behavior. The goal is to better understand habitat use and movement ecology while developing reproducible workflows for biologging data analysis.

---

## Study Area
- **Expected migration region:**
  - Latitude: 15°N – 35°N
  - Longitude: 120°E – 145°E

This bounding box covers the western North Pacific, including release and recapture locations.

---

## Tag Specifications
- **Tag model:** MiniPAT (Wildlife Computers)
- **Measured parameters:** depth (m), temperature (°C), relative light intensity
- **Sampling interval :**
  - **Raw archival sampling interval:** 1 seconds; **independent** of the transmitted time-series interval.
  - **Satellite-transmitted time series:** options are **75, 150, 300, 450, or 600 seconds** (i.e., 1.25–10 minutes). Our dataset uses **5 minutes (300 s)**.
- **Deployment & recapture:**
  - Release: reported by fishers (lat/lon at deployment)
  - Recapture: positions derived from Argos satellite when the tag surfaces
  - Direct retrieval: in some cases (e.g., Tag ID 208992), tags were physically recovered with complete raw data
- **Specifications:** [MiniPAT tag information](https://wildlifecomputers.com/our-tags/pop-up-satellite-tags-fish/minipat/)

---

## Data Description
- **Depth & temperature:**
  - **Transmitted time series:** 5-minute interval (300 s) in this dataset
  - Rapid vertical movements (~500 m within 5 minutes) were observed, consistent with squid behavior


---

## Release and Pop-up Locations
|   Argos ID |   Mantle length (cm) | Sex     | Release Date (UTC)   |   Release Lat |   Release long | Pop-up date (UTC)   |   Pop-up Lat |   Pop-up Long |
|-----------:|---------------------:|:--------|:---------------------|--------------:|---------------:|:--------------------|-------------:|--------------:|
|     208993 |                   82 | Male    | 2021-03-25 09:14:00  |       27.85   |        132.43  | 2021-03-29 09:13:52 |      27.205  |       131.837 |
|     228038 |                   72 | Female  | 2022-04-27 05:37:00  |       26.9128 |        133.475 | 2022-05-07 00:17:01 |      27.0335 |       132.023 |
|     228040 |                   68 | Male    | 2022-03-21 08:01:00  |       25.5678 |        131.818 | 2022-04-06 21:50:59 |      23.8889 |       128.67  |
|     203226 |                   69 | Male    | 2021-02-22 03:52:00  |       23.5603 |        122.647 | 2021-03-14 08:33:00 |      23.9162 |       122.149 |
|     208991 |                   70 | Male    | 2021-02-22 04:31:00  |       23.5798 |        122.646 | 2021-03-14 08:32:00 |      22.113  |       124.049 |
|     208992 |                   80 | Male    | 2021-02-22 05:08:00  |       23.5946 |        122.645 | 2021-02-25 08:22:37 |      23.8425 |       122.914 |
|     208995 |                   81 | Unknown | 2022-01-25 04:05:00  |       22.8535 |        124.847 | 2022-01-30 00:24:54 |      21.624  |       124.926 |
|     208996 |                   75 | Male    | 2022-01-25 04:33:00  |       22.84   |        124.844 | 2022-03-03 21:22:26 |      21.0638 |       122.865 |
|     228035 |                   80 | Male    | 2022-04-06 04:28:00  |       23.6667 |        122.783 | 2022-04-14 08:23:21 |      22.834  |       123.111 |
|     228036 |                   80 | Unknown | 2022-04-06 05:55:00  |       23.7    |        122.783 | 2022-05-03 02:53:08 |      28.239  |       127.24  |



---

## Methodology
- **Tag Data Handling:**  
  Method for extracting tag information from MiniPAT to create input for PANGEO-FISH.  
  - All timestamps converted to **UTC** for consistency  
  - Input organized per individual (tag ID) with dedicated folders  
  - Transmitted time series conversion to PANGEO-FISH input: **@notebook link here**  @etienne
  - Recovered tag time series conversion to PANGEO-FISH input: **@notebook link here**  @etienne

- **Position Estimation:**  
  - Performed with **PANGEO-FISH** using depth & temperature matching against ocean model fields  
    - @notebook link here @etienne put in ./calculation/
  - Ocean model sources:  
    - Copernicus Marine Service (daily, ~10 km resolution)  
      - @etienne Link to the input indicated in the above notebook  

  - Bathymetry sources:  
    - @etienne to update the source of bathymetry:cf link to where you downloaded.   
      
- **Result analysis :**  
  - notebook for S1(variance), S3(each tag), Fig2(all tag) @etienne.
 
    


