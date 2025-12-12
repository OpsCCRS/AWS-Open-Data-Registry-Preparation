**CCRS MODIS Albedo Over Canada at 250-m Resolution and 10-day Intervals**

**1. Product Overview**

The **CCRS MODIS albedo over Canada at 250-m resolution** (called below
for brevity as **CCRS MODIS albedo)** product provides regional,
long-term, and consistent time series of surface spectral and broadband
reflectances and albedo as well as associated quality layer and some
associated parameters produced at 10-day intervals (three per month).

This product is an Earth Observation (EO) analysis-ready dataset,
generated from the Moderate Resolution Imaging Spectroradiometer (MODIS)
level 1B imagery from the MODIS imager aboard the Terra satellite
collection (6.1).

-   **Temporal Resolution:** 10-day composite product.

-   **Spatial Resolution:** 250 meters.

-   **Key Indices:** Spectral and broadband albedo and reflectances.

-   **Data Format:** Cloud Optimized GeoTIFF (COG)

**2. Data Access and Organization**

The dataset is publicly hosted on the Amazon Web Services (AWS) Open
Data Registry.

**2.1 S3 Bucket Location**

-   **Bucket Name:**

-   **Access:**

**2.2 File Naming Convention**

Each COG file follows the naming convention as below:

Terra\_MODIS\_BX\_Albedo.Noon\_250m\_YYYYMMDD.tif

Terra\_MODIS\_BX\_BRDF.Norm\_250m\_YYYYMMDD.tif

Terra\_MODIS\_Index\_BRDF.Norm\_250m\_YYYYMMDD.tif

Terra\_MODIS\_NDVI\_250m\_YYYYMMDD.tif

Terra\_MODIS\_VIS\_BB\_Albedo.Noon\_250m\_YYYYMMDD.tif

Terra\_MODIS\_NIR\_BB\_Albedo.Noon\_250m\_YYYYMMDD.tif

Terra\_MODIS\_SW\_BB\_Albedo.Noon\_250m\_YYYYMMDD.tif

Terra\_MODIS\_Snow\_Fraction\_250m\_YYYYMMDD.tif

Terra\_MODIS\_Snow\_GrainSize\_1.0km\_YYYYMMDD.tif

Terra\_MODIS\_State\_Mask\_250m\_YYYYMMDD.tif

| **Component**        | **Description**                                                                                                                                                                                                                                              | **Example**          |
|----------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------|
| BX\_Albedo.Noon      | Band X spectral albedo, where X may have values from 1 to 7, which are used to identify MODIS land bands 1 to 7. Spectral albedo values computed at the local solar noon geometry. Stored as two-byte integer values scaled by factor 10,000                 | B1\_Albedo.Noon      |
| BX\_BRDF.Norm        | Band X spectral reflectances for MODIS land bands 1 to 7. Spectral reflectance values correspond to spectral reflectances for band BX(X=1-7) normalized to a nadir view and overhead sun geometry. Stored as two-byte integer values scaled by factor 10,000 | B1\_BRDF.Norm        |
| Index\_BRDF          | Index file that contains 2-byte integer value (I2) used for BRDF sampling and fitting and computed as described in the data format description document https://data.eodms-sgdot.nrcan-rncan.gc.ca/public/CCRS/Trishchenko_MODIS_Albedo/                   | Index\_BRDF          |
| NDVI                 | Normalized Difference Vegetation Index. Stored as two-byte integer values scaled by factor 10,000.                                                                                                                                                           | NDVI                 |
| VIS\_BB\_Albedo.Noon | Broadband visible albedo computed at the local solar noon geometry. Stored as two-byte integer values scaled by factor 10,000.                                                                                                                               | VIS\_BB\_Albedo.Noon |
| NIR\_BB\_Albedo.Noon | Broadband NIR albedo computed at the local solar noon geometry. Stored as two-byte integer values scaled by factor 10,000.                                                                                                                                   | NIR\_BB\_Albedo.Noon |
| SW\_BB\_Albedo.Noon  | Broadband SW (shortwave) albedo computed at the local solar noon geometry. Stored as two-byte integer values scaled by factor 10,000.                                                                                                                        | SW\_BB\_Albedo.Noon  |
| Snow\_Fraction       | Snow fraction stored as 1-byte signed integer that varies from 0 to 100, i.e., corresponds to snow fraction expressed in percent                                                                                                                             | Snow\_Fraction       |
| Snow\_GrainSize      | The estimates of snow grain size in \[um\] averaged over 4 × 4 original 250-m pixels, i.e. over 1km × 1km area                                                                                                                                               | Snow\_GrainSize      |
| State\_Mask          | contains the following values coded as 1-byte integers: 1 – vegetated land, 2 – barren land, 3 – water/land mix, 4 - water, 5 -snow/ice, 10 – cloud.                                                                                                         | State\_Mask          |
| YYYYMMDD             | Start date of the composite interval                                                                                                                                                                                                                         | 20000501             |

**3. Data Dictionary and Schema**

Each file contains one science data set.

The CCRS Albedo dataset includes times series of 10-day composite
products derived at 250-m spatial resolution over Canadian territory and
neighboring areas produced at the Canada Centre for Remote Sensing
(CCRS) since February 2000. The datasets contain spectral and broadband
reflectances and albedo for MODIS bands B1-B7 designed primarily for
land applications. The input level 1B imagery for all spectral bands was
downscaled and re-projected into the Lambert Conformal Conic (LCC)
projection at 250-m spatial resolution. The area size is 5,700 km ×
4,800 km. The specialized MODIS processing system was developed at CCRS
to fully utilize the high quality of MODIS L1B swath imagery over the
northern latitudes. As such, the CCRS Albedo product is different from
the standard NASA product. The differences are related to temporal and
spatial scaling, shape of kernel functions employed to fit data, as well
as details of scene identification, atmospheric correction, and data
fitting methodology.

The regular temporal composite intervals start on day 1, 11, and 21 of
each month. There are three composite intervals per month. The last
composite interval of the month may include 10 or 11 days, except in
February, where it may include 8 or 9 days depending on whether it is a
regular or a leap year.

**Key Data Layers (Science Data Sets)**

| **Dataset Name**     | **Type**                                        | **Description**                                                                                                                                                                                    | **Units/Interpretation**                                                                     | **Scale Factor** | **Fill Value** |
|----------------------|-------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------|------------------|----------------|
| BX\_Albedo.Noon      | 16-bit signed integer                           | Band X spectral albedo, where X may have values from 1 to 7, which are used to identify MODIS land bands 1 to 7. Spectral albedo values computed at the local solar noon geometry                  | Unitless. Range: 0 to +1.0                                                                   | **0.0001**       | 0              |
| BX\_BRDF.Norm        | 16-bit signed integer                           | Band X spectral reflectances for MODIS land bands 1 to 7. Spectral reflectance values correspond to spectral reflectances for band BX(X=1-7) normalized to a nadir view and overhead sun geometry. | Unitless. Range: 0 to +1.0                                                                   | **0.0001**       | 0              |
| Index\_BRDF          | 16-bit unsigned integer                         | Quality assessment (QA) flag for BRDF sampling and fitting process                                                                                                                                 | Bit Flags (Requires Bitwise Decoding)                                                        | N/A              | 0              |
| NDVI                 | 16-bit signed integer                           | Normalized Difference Vegetation Index.                                                                                                                                                            | Unitless. Range: -1.0 to +1.0                                                                   | **0.0001**       | 32767 (\#7FFF) |
| VIS\_BB\_Albedo.Noon | 16-bit signed integer                           | Broadband visible albedo computed at the local solar noon geometry.                                                                                                                                | Unitless. Range: 0 to +1.0                                                                   | **0.0001**       | 0              |
| NIR\_BB\_Albedo.Noon | 16-bit signed integer                           | Broadband NIR albedo computed at the local solar noon geometry.                                                                                                                                    | Unitless. Range: 0 to +1.0                                                                   | **0.0001**       | 0              |
| SW\_BB\_Albedo.Noon  | 16-bit signed integer                           | Broadband Sw albedo computed at the local solar noon geometry.                                                                                                                                     | Unitless. Range: 0 to +1.0                                                                   | **0.0001**       | 0              |
| Snow\_Fraction       | 1-byte signed integer that varies from 0 to 100 | Snow fraction stored as 1-byte signed integer that varies from 0 to 100, i.e., corresponds to snow fraction expressed in percent                                                                   | Unitless. Range: 0 to +1.0                                                                   | 0.01             | 255 (\#FF)     |
| Snow\_GrainSize      | 16-bit signed integer                           | The estimates of snow grain size in \[um\] averaged over 4 × 4 original 250-m pixels, i.e. over 1km × 1km area                                                                                     | Micron, typical range from \~ 30 um to 2000 um                                               | 1                | 0              |
| State\_Mask          | 8-bit unsigned integer                          | Surface state of cloud flag                                                                                                                                                                        | 1 – vegetated land, 2 – barren land, 3 – water/land mix, 4 - water, 5 -snow/ice, 10 – cloud. | N/A              | 255 (\#FF)     |

**Data Interpretation**

To convert the raw digital numbers (DN) to physical values (PV) of
albedo, reflectance or NDVI, users **MUST** apply the scale factor:

PV=DN\*0.0001

For example, DN=1500 means 0.15 for PV.

The Fill Value represents invalid or non-existing data. Values outside the range should be considered invalid.

**Quality Assurance**

The Quality Assurance (QA) information is essential. This information is
available from the State Mask and Index\_BRDF file.

**4. Geographic and Spatial Information**

**4.1 Projection System**

The imagery is produced in the Lambert Conformal Conic (LCC) projection
at 250-m spatial resolution. The area size is 5,700 km × 4,800 km. The
parameters of the Lambert Conformal Conic (LCC) projection used for
output imagery over Canada are given in Table 1

Table 1. The parameters of the map projection

| **Parameter**            | **Value**                                |
|--------------------------|------------------------------------------|
| *Projection*             | Lambert Conformal Conic (LCC)            |
| 1<sup>st</sup> parallel  | 49.00 \[degree\]                         |
| 2<sup>nd</sup> parallel  | 77.00 \[degree\]                         |
| Central meridian         | –95.00 \[degree\]                        |
| Upper left corner        | (–2600000.0 E \[m\]; 10500000.0 N \[m\]) |
| Lower right corner       | (3100000.0 E \[m\]; 5700000.0 N \[m\])   |
| Easting                  | 0                                        |
| Northing                 | 0                                        |
| Gridbox size, x          | 250 \[m\]                                |
| Gridbox size, y          | 250 \[m\]                                |
| Number of pixels along x | 22800                                    |
| Number of pixels along y | 19200                                    |

The georeferencing details in GEOTIFF files are provided in the ENVI
header files generated together with data files. This information is
included in the header file as follows:

map info = {Lambert Conformal Conic, 1, 1, -2600000, 10500000, 250,
250,WGS-84})

projection info = {4, 6378137, 6356752.314245179, 0, -95, 0, 0, 49,
77,WGS-84, Lambert Conformal Conic})

coordinate system string =
{PROJCS\["Lambert\_Conformal\_Conic",GEOGCS\["GCS\_WGS\_1984",DATUM\["D\_WGS\_1984",SPHEROID\["WGS\_1984",6378137.0,298.257223563\]\],PRIMEM\["Greenwich",0.0\],UNIT\["Degree",0.017453292519943295\]\],PROJECTION\["Lambert\_Conformal\_Conic"\],PARAMETER\["False\_Easting",0.0\],PARAMETER\["False\_Northing",0.0\],PARAMETER\["Central\_Meridian",-95.0\],PARAMETER\["Standard\_Parallel\_1",49.0\],PARAMETER\["Standard\_Parallel\_2",77.0\],PARAMETER\["Scale\_Factor",1.0\],PARAMETER\["Latitude\_Of\_Origin",0.0\],UNIT\["Meter",1\]\]})

**4.2 Tiling System**

The data is delivered as one map (file) for the entire area for each
parameter. An example, of the false color image is given in Figure 1.

<img width="839" height="716" alt="image" src="https://github.com/user-attachments/assets/68d5f62a-faa1-4a53-a74d-dd315bfd2a79" />


Figure 1. An example of the false colour image for coverage area used
for CCRS albedo mapping.
