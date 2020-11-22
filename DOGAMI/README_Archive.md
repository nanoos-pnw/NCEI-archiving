# DOGAMI Shoreline Profile Data

NANOOS - DOGAMI Oregon Beach and Shoreline Mapping Analysis Program (OBSMAP) dataset

- [DOGAMI: Oregon Department of Geological and Mineral Industries](https://www.oregongeology.org)
- [NANOOS: Northwest Association of Networked Ocean Observing System](http://www.nanoos.org)

This dataset contains data from a set of discrete shoreline **transects** within a single **littoral cell** (region) along the Oregon coast. **Surveys** are carried out at each transect at seasonal to annual time scales. These transects show the degree of change (horizontal and vertical) taking place across the sub-aerial beach down into the inter-tidal zone; the data represent discrete stations (points) along the shore. Transect plots for this and all other littoral cells are available on the [NANOOS Visualization System (NVS) Beach and Shoreline Changes App](http://nvs.nanoos.org/BeachMapping).

Easting, northing and surface elevation data are provided at each survey point. From late Summer 1997 through Summer 2002, data was generated from profiles interpolated from an airborne LIDAR survey. Surveys using Real-Time Kinematic Differential Global Positioning System (RTK-DGPS) instruments started in October 2004.

**TODO:** Use place holder "variables" to populate the README file with information for the littoral cells:
- NCEI dataset generation date
- Name
- Number of transects
- Date of most recent survey
- Projection used in this dataset

## Projection information

- projection switch based on latitude being N or S of Florence, OR (44.01 N)
- NAD83 Oregon State Plane North | South: 32126 | 32127
- http://epsg.io/32127
- Easting and northing values are cartesisan coordinates, with positive East and North.

## Points of Contact

(**TODO:** Use role descriptions from the IOOS Metadata Profile and CMOP NCEI archive netcdf files)

- Publisher Contact: NANOOS Data Manager, nanoos.dmac@gmail.com
- Technical Point of Contact: Jonanthan Allan, DOGAMI, Jonathan.ALLAN@oregon.gov

## Dataset files

In addition to this README file, this dataset contains the following files:

1. Transect data files. 1 per transect, containing data from all surveys for the transect.
2. Littoral cell inventory files. One file in CSV format and one in GeoJSON, containing the same information.
3. FGDC metadata file. Transect metadata in XML format following the FGDC standard.

### 1. Transect data files

Data from all surveys conducted on a transect are stored in a single CSV file. Each row represents one survey point, and rows are ordered by survey date (earliest to latest) and survey point (start to end points).

File names follow the following convention: 

`Bayocean_[transect]_transect_data_prj_epsg32126.csv`

where `Bayocean` is the short littoral cell name, `[transect]` is the transect code (see the littoral cell inventory), and `epsg32126` is the EPSG code for the Oregon State Plane projection used in the transect. Example: `Bayocean_Bay1_transect_data_prj_epsg32126.csv`.

**Attribute descriptions:**

| Field | Description | Example
--------|-------------|--------
| survey_number | Incremental survey number starting from the first survey (1) | 1
| survey_date | Date survey was conducted | 1997-10-18
| point_number | Incremental survey-specific point number starting with 1 | 1
| easting_meters | Oregon State Plane easting (meters) coordinate in the transect projection | 2229807.882
| northing_meters | Oregon State Plane northing (meters) coordinate in the transect projection | 209765.088
| distance_meters | Distance from the survey start point (meters) | 0.000
| elevation_meters | Surface elevation (meters) | 4.082
| measurement_approach | Elevation and coordinate measurement approach (LIDAR or GPS) | LIDAR

### 2. Littoral cell inventory files

Summary information for each transect is compiled as a littoral cell inventory available in two formats: a tabular CSV file (**Bayocean_littoralcell_inventory.csv**) and a [GeoJSON](https://en.wikipedia.org/wiki/GeoJSON) file (**Bayocean_littoralcell_inventory.geojson**) depicting transect lines by connecting the start and end points (in latitude and longitude coordinates), which can be visualized and browsed using Geographical Information System (GIS) software. The two files contain the same information.

**Attribute descriptions:**

| Attribute | Description | Example
------------|-------------|--------
transect | Transect code used in file names | Bay1
littoralcell | Short littoral cell name used in file names | Bayocean
littoralcell_fullname | Complete littoral cell name | Bayocean Spit
state | State where the transect is found | Oregon
provider | Dataset provider | DOGAMI-NANOOS
projection | State Plane projection used in the transect data easting and northing coordinates | epsg:32126
survey_count | Number of surveys carried out at this transect | 53
date_first | Date of first transect survey | 1997-10-18
date_last | Date of last transect survey | 2018-12-10
longitude | Longitude of transect median point | -123.9601
latitude | Latitude of transect median point | 45.5025
start_lon | Longitude of transect start (first point) | -123.9585
start_lat | Latitude of transect start (first point) | 45.5023
end_lon | Longitude of transect start (end point) | -123.9629
end_lat | Latitude of transect start (end point) | 45.5027

Latitude and longitude WGS 84 (EPSG:4326) coordinates are in decimal degrees. The following values are identical for all transects in this littoral cell dataset: littoralcell, littoralcell_fullname, state, provider and projection.

### 3. FGDC metadata file

Littoral cell metadata file in FGDC XML format.
