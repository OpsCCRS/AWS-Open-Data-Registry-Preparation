**CCRS Multi-Spectral Clear-Sky Composites of MODIS/Terra Land Channels Over Canada at 250m:**   
**Descriptive Documentation**

**1\. Product Overview**

The CCRS Multi-Spectral Clear-Sky Composites of MODIS/Terra Land Channels Over Canada at 250m (referred to below as CCRS MODIS Clear-Sky Composites over Canada) provides regional, long-term, and consistent 10-day time series products (three per month) of Top of Atmosphere (TOA) reflectance, along with associated ancillary layers.

This product is an Earth Observation (EO) analysis-ready dataset, generated from the Moderate Resolution Imaging Spectroradiometer (MODIS) level 1B imagery from the MODIS imager aboard the Terra satellite collection (6.1).

* **Temporal Resolution:** 10-day composite product.  
* **Spatial Resolution:** 250 meters.  
* **Data Format:** Cloud Optimized GeoTIFF (COG)

**2\. Data Access and Organization**

The dataset is publicly hosted on the Amazon Web Services (AWS) Open Data Registry.

**2.1 S3 Bucket Location**

* **Bucket Name:** ccrs-modis- composite  
* **Access:** S3 URI (s3://ccrs-modis- composite /); URL (https\://ccrs-modis- composite.s3.ca-central-1.amazonaws.com/)

**2.2 File Naming Convention**

Each COG file follows the naming convention as below:

Terra\_MODIS\_B1\_RETOA\_250m\_BKW\_YYYYMMDD.tif  
Terra\_MODIS\_B2\_RETOA\_250m\_BKW\_YYYYMMDD.tif  
Terra\_MODIS\_B3\_RETOA\_250m\_BKW\_YYYYMMDD.tif  
Terra\_MODIS\_B4\_RETOA\_250m\_BKW\_YYYYMMDD.tif  
Terra\_MODIS\_B5\_RETOA\_250m\_BKW\_YYYYMMDD.tif  
Terra\_MODIS\_B6\_RETOA\_250m\_BKW\_YYYYMMDD.tif  
Terra\_MODIS\_B7\_RETOA\_250m\_BKW\_YYYYMMDD.tif  
Terra\_MODIS\_Rel\_Date\_250m\_BKW\_YYYYMMDD.tif  
Terra\_MODIS\_Satellite\_Azimuth\_250m\_BKW\_YYYYMMDD.tif  
Terra\_MODIS\_Satellite\_Zenith\_250m\_BKW\_YYYYMMDD.tif  
Terra\_MODIS\_Sun\_Azimuth\_250m\_BKW\_YYYYMMDD.tif  
Terra\_MODIS\_Sun\_Zenith\_250m\_BKW\_YYYYMMDD.tif  
Terra\_MODIS\_State\_Flag\_250m\_BKW\_YYYYMMDD.tif  
Terra\_MODIS\_RETOA\_RGB\_2.5km\_BKW\_YYYYMMDD.tif  
Terra\_MODIS\_B1\_RETOA\_250m\_FRW\_YYYYMMDD.tif  
Terra\_MODIS\_B2\_RETOA\_250m\_FRW\_YYYYMMDD.tif  
Terra\_MODIS\_B3\_RETOA\_250m\_FRW\_YYYYMMDD.tif  
Terra\_MODIS\_B4\_RETOA\_250m\_FRW\_YYYYMMDD.tif  
Terra\_MODIS\_B5\_RETOA\_250m\_FRW\_YYYYMMDD.tif  
Terra\_MODIS\_B6\_RETOA\_250m\_FRW\_YYYYMMDD.tif  
Terra\_MODIS\_B7\_RETOA\_250m\_FRW\_YYYYMMDD.tif  
Terra\_MODIS\_Rel\_Date\_250m\_FRW\_YYYYMMDD.tif  
Terra\_MODIS\_Satellite\_Azimuth\_250m\_FRW\_YYYYMMDD.tif  
Terra\_MODIS\_Satellite\_Zenith\_250m\_FRW\_YYYYMMDD.tif  
Terra\_MODIS\_Sun\_Azimuth\_250m\_FRW\_YYYYMMDD.tif  
Terra\_MODIS\_Sun\_Zenith\_250m\_FRW\_YYYYMMDD.tif  
Terra\_MODIS\_State\_Flag\_250m\_FRW\_YYYYMMDD.tif  
Terra\_MODIS\_RETOA\_RGB\_2.5km\_FRW\_YYYYMMDD.tif  
Terra\_MODIS\_State\_Stat\_250m\_YYYYMMDD.tif

The detailed of each file naming is included in Table 1\.

**Table 1\. Key Data Layers (Science Data Sets)**

| IMAGE LAYER | DESCRIPTION | DATA TYPE | FILL VALUE | VALID RANGE | SCALE FACTOR | OFF-SET | Unit |
| :---: | :---: | :---: | ----- | ----- | :---: | :---: | :---: |
| B\#\#\_RETOA  | Band \#\# reflectance at TOA | 16-bit signed | \-1 | 1\~32767 | 0.0001 | 0 | None |
| Rel\_Date | Time of observation relative to start time (normally assigned in Composite\_setup file) | 16-bit unsigned | 65535 | 0\~44640 | 1 | 0 | Minute |
| Sun\_Zenith | Solar zenith  | 16-bit signed | 32767 | 0\~9000 | 0.01 | 0 | Degree |
| Satellite\_Zenith | Satellite zenith  | 16-bit signed | 32767 | 0\~9000 | 0.01 | 0 | Degree |
| Sun\_Azimuth | Sun azimuth  | 16-bit signed | 32767 | \-18000\~ 18000 | 0.01 | 0 | Degree |
| Satellite\_Azimuth | Satellite azimuth  | 16-bit signed | 32767 | \-18000\~ 18000 | 0.01 | 0 | Degree |
| State\_Flag |  Decimal index of pixel state   | 8-bit unsigned integer |   255 |   The units decimal digit:      0 \- land pixel;      1 \- water/land mixture pixel;      2 \- water pixel;      3 \- snow/ice   The 10s decimal digit:      0 \- clear sky;      1 \- cloud shadow;      2 \- cloud.   The 100s decimal digit:      0 \- backward scattering geometry;      1 \- forward scattering geometry.. |  |  |  |
| State\_Stat | Binary mask | 16-bit unsigned mask | 0 | State\_Stat is bit mask 2-byte value= \#\_icecloud\*4096+\#\_snow\*256+\#\_water\*16+\#\_land. It is 4-part value with each part equal to 4 bits, i.e. (4 x 4 bits) total 1st 4 bits (rightmost): number of scenes with class land (\<=15) 2nd 4 bits: number of scenes with class water (\<=15) 3rd 4 bits: number of scenes with class snow (\<=15) 4th 4 bits: number of scenes with class ice cloud (\<=15) Missing value: 0 |  |  |  |
| YYYYMMDD | Start date of the composite interval |  |  |  |  |  |  |

**3\. Data information**

Each file contains one science data set. 

The MODIS Clear-Sky Composites over Canada at the Top of the Atmosphere (TOA) Dataset include times series of 10-day composite products derived at 250-m spatial resolution over Canadian territory and neighboring areas produced at the Canada Centre for Remote Sensing (CCRS) since February 2000\. The datasets contain clear-sky composite for MODIS bands B1-B7 designed primarily for land applications. Each ten-day composite period includes two sets of clear-sky composites, 1\) for the forward (FRW) scattering direction, and 2\) backward (BKW) scattering direction. The imagery for all spectral bands was downscaled and re-projected into the Lambert Conformal Conic (LCC) projection at 250-m spatial resolution. The area size is 5,700 km × 4,800 km. The specialized MODIS processing system was developed at CCRS to fully utilize the high quality of MODIS L1B swath imagery over the northern latitudes. As such, the CCRS MODIS Clear-sky Product is different from the standard NASA product. The differences are related to temporal and spatial scaling, as well as details of remapping, scene identification and clear-sky compositing approach. 

**Data Interpretation**

Data in Band Reflectance layers are stored as 2-byte integer values. The parameters are scaled by a factor 10,000, i.e. real value of parameter (RV) shall be computed from stored value (I2) as follows

RV=I2/10000

The “State\_Flag” files contain 1-byte bit mask and “State\_Stat” file contains 2-byte mask with the content described in Table 1\. 

Various angles are expressed in degrees multiplied by 100 and written as 2-byte integer values. 

**4\. Geographic and Spatial Information**

**4.1 Projection System**

The imagery is produced in the Lambert Conformal Conic (LCC) projection at 250-m spatial resolution.  The area size is 5,700 km × 4,800 km. The parameters of the Lambert Conformal Conic (LCC) projection used for output imagery over Canada are given in Table 2\.

**Table 2\. The parameters of the map projection**

| Parameter | Value |
| ----- | :---: |
| *Earth ellipsoid* | GRS 1980 |
| Major semi-axis, a | 6378137 \[m\] |
| First eccentricity | 0.00669438002290 |
| Ellipsoid flattening, f | 0.00335281068118 |
| *Projection* | LCC |
| 1st parallel | 49.00 \[degree\] |
| 2nd parallel | 77.00 \[degree\] |
| Central meridian | –95.00 \[degree\] |
| Upper left corner  | (–2600000.0 E \[m\]; 10500000.0 N \[m\]) |
| Lower right corner | (3100000.0 E \[m\]; 5700000.0 N \[m\]) |
| Easting | 0 |
| Northing | 0 |
| Gridbox size, x | 250 \[m\] |
| Gridbox size, y | 250 \[m\] |
| Number of pixels along x | 22800 |
| Number of pixels along y | 19200 |

The georeferencing details in GEOTIFF files are provided in the ENVI header files generated together with data files. This information is included in the header file as follows

map info \= {Lambert Conformal Conic, 1, 1, \-2600000, 10500000, 250, 250, WGS-84})  
projection info \= {4, 6378137, 6356752.314245179, 0, \-95, 0, 0, 49, 77, WGS-84, Lambert Conformal Conic})  
coordinate system string \= {PROJCS\["Lambert\_Conformal\_Conic",GEOGCS\["GCS\_WGS\_1984",DATUM\["D\_WGS\_1984",SPHEROID\["WGS\_1984",6378137.0,298.257223563\]\],PRIMEM\["Greenwich",0.0\],UNIT\["Degree",0.017453292519943295\]\],PROJECTION\["Lambert\_Conformal\_Conic"\],PARAMETER\["False\_Easting",0.0\],PARAMETER\["False\_Northing",0.0\],PARAMETER\["Central\_Meridian",-95.0\],PARAMETER\["Standard\_Parallel\_1",49.0\],PARAMETER\["Standard\_Parallel\_2",77.0\],PARAMETER\["Scale\_Factor",1.0\],PARAMETER\["Latitude\_Of\_Origin",0.0\],UNIT\["Meter",1\]\]})

**4.2 Tiling System**

The data is delivered as one map (file) for the entire area for each parameter. An example, of the false color image is given in Figure 1\. 

![A map of the worldAI-generated content may be incorrect.][image1]

Figure 1\. An example of the false colour image for coverage area used for CCRS Clear Sky composite mapping. 

[image1]: 
