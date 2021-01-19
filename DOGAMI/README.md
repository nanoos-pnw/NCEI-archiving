# README

- Draft README file for archive files: [README_Archive.md](https://github.com/nanoos-pnw/NCEI-archiving/blob/master/DOGAMI/README_Archive.md)
- See sample files at http://data.nanoos.org/ncei/dogami/
- Littoral Cells in initial archiving batch: Bayocean, Nehalem, Neskowin, Rockaway
- [Littoral Cell inventory sample on GitHub](https://github.com/nanoos-pnw/NCEI-archiving/blob/master/DOGAMI/Bayocean_littoralcell_inventory.geojson); GeoJSON files on GitHub are rendered on an interactive, Google-Maps-type map
- Sample NANOOS (OHSU-CMOP/CRITFC) dataset archived at NCEI: https://data.nodc.noaa.gov/cgi-bin/iso?id=gov.noaa.nodc:0161524

# Archive SOP
* Each Archival Information Package (AIP) will consist of a single littoral cell. Currently there are **how many?** littoral cells.
  * See [below](#package-sizes) for an approximation of the size for each SIP.
* Each directory at http://data.nanoos.org/ncei/dogami/ is a littoral cell Submission Information Package (SIP) and will follow the BagIt convention.
* The packages will be updated at a frequency **weekly?monthly?yearly?**.
* NCEI will check for new packages every **month?year?**
* The BagIt convention will be used to validate the transfer to NCEI.
* For new littoral cell submissions (ones that NCEI hasn't made an AIP for yet)
  * The package will be tranferred to NCEI.
  * **Do something with the information in the bag-info.txt file?**
  * Once the package has been verified, the supplementary BagIt files will be discarded as they are artifacts from the transfer.
  * All of the files in the `data/` will be used to create a new AIP. The directory `data/` will not be preserved, only the data files contained within.
  * Extract the metadata from the data and metadata files to populate the AIP metadata record. See the [metadata mapping table](#metadata-mapping).
* Updates to already archived packages:
  * NANOOS will update the *entire* littoral cell package on their server.
  * NCEI will check the **checksums/file creation date/start date-end date range/something else??** against the existing AIP to verify the package should be updated.
  * NCEI will perform a *major revision* replacing the existing AIP with the new data on the NANOOS server.
  * The AIP metadata record will be updated to reflect the replacement data.
* The data will be served according to Tier 1 stewardship (basic access), with the hopes that NCEI can make the geojson inventory files accessible using advanced access services.
  
* **The FGDC metadata file will be transformed to ISO19115-2 at NCEI?**

## NCEI checks on the package
1. Package structure follows the identified [BagIt structure below](#submission-information-package-structure).
1. Checksums match.
1. Latitude and Longitude values in the inventory are reasonable. Do we want to check against a bounding box?
1. File names match the identified convention described in [README_Archive.md](https://github.com/nanoos-pnw/NCEI-archiving/blob/master/DOGAMI/README_Archive.md)
1. **Other checks?**

### Submission Information Package structure
This sections contains an example from the Rockaway littoral cell submission information package.
```
ROCKAWAY
|   bag-info.txt
|   bagit.txt
|   manifest-sha256.txt
|   tagmanifest-sha256.txt
|
\---data
        README.md
        Rockaway_FGDC_Metadata.xml
        Rockaway_littoralcell_inventory.csv
        Rockaway_littoralcell_inventory.geojson
        Rockaway_Rck10_transect_data_prj_epsg32126.csv
        Rockaway_Rck1_transect_data_prj_epsg32126.csv
        Rockaway_Rck2_transect_data_prj_epsg32126.csv
        Rockaway_Rck3_transect_data_prj_epsg32126.csv
        Rockaway_Rck4_transect_data_prj_epsg32126.csv
        Rockaway_Rck5_transect_data_prj_epsg32126.csv
        Rockaway_Rck6_transect_data_prj_epsg32126.csv
        Rockaway_Rck7_transect_data_prj_epsg32126.csv
        Rockaway_Rck8_transect_data_prj_epsg32126.csv
        Rockaway_Rck9_transect_data_prj_epsg32126.csv
```

### Package sizes
These are approximate sizes of the entire SIP for four littoral cells. The AIP's will be slightly smaller (KB's) because the ancillary BagIt files will not be included.

| Package | SIP Size
----------|---------
| Bayocean | 5.2M 
| Nehalem | 6.2M 
| Neskowin | 7.2M   
| Rockaway | 5.7M 

### Metadata mapping
This section documents how the NCEI metadata record will be populated. If the contents are a path, then that information will be extracted from the FGDC xml file. Otherwise, the information will be extracted from the data file(s) or used verbatim as listed.

| Metadata source | NCEI element |
--------------|---------------
| `metadata/idinfo/citation/citeinfo/title` | title
| `metadata/idinfo/descript/abstract` | abstract
| `metadata/idinfo/ptcontac/cntinfo/cntperp/cntper` | contact
| **NANOOS Data Manager** | submitter
| **NANOOS** | submitting institution
| `metadata/idinfo/ptcontac/cntinfo/cntorgp/cntorg` | collecting institution
| extract the latitude/longitude from the inventory file `latitude` and `longitude` columns and calculate the min/max | lat/lon min/max
| extract `survey_date` column from all the data files and compute the min/max | start date/end date
| `metadata/idinfo/keywords/place` | sea names
|  | observation types
|  | instrument types
|  | data types
|  | contributing projects
|  | platforms
| sum of the number of data lines in each data file in the AIP. | number of observations
| Extract out each `themekey` term within `metadata/idinfo/keywords/theme/` and information from `metadata/idinfo/keywords/stratum/` | supplementary information
 
#### Start date and bounding box information extracted from example packages
littoralcell | count |start date | end date | lat min | lat max | lon min | lon max
-------------|-------|-------|------|---------|---------|---------|--------	
Bayocean | 5296 | 1997-10-18 | 2018-12-10 | 45.5025 | 45.5595 | -123.9601 | -123.9506
Nehalem | 109398 | 1997-10-18 | 2018-12-06 | 45.6635 | 45.7296 | -123.9452 | -123.9399
Neskowin | 128483 | 1997-10-18 | 2019-03-25 | 45.1045 | 45.2128 | -123.9858 | -123.9690
Rockaway | 99880 | 1997-10-18 | 2018-12-07 | 45.5740 | 45.6531 | -123.9566 | -123.9419
