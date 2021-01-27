# DOGAMI-NANOOS Oregon Beach and Shoreline Mapping Analysis Program (OBSMAP) dataset: Rockaway Littoral Cell

- DOGAMI: Oregon Department of Geological and Mineral Industries, [https://www.oregongeology.org](https://www.oregongeology.org)
- NANOOS: Northwest Association of Networked Ocean Observing System, [http://www.nanoos.org](http://www.nanoos.org)

2021-01-26

This dataset contains data from a set of discrete shoreline **transects** within a single **littoral cell** (region) along the Oregon coast. **Surveys** are carried out at each transect at seasonal to annual time scales. These transects show the degree of change (horizontal and vertical) taking place across the sub-aerial beach down into the inter-tidal zone; the data represent discrete stations (points) along the shore. Transect plots for this and all other littoral cells are available on the NANOOS Visualization System (NVS) Beach and Shoreline Changes App, [http://nvs.nanoos.org/BeachMapping](http://nvs.nanoos.org/BeachMapping).

Easting, northing and surface elevation were measured at each survey point. From late Summer 1997 through Summer 2002, data was generated from profiles interpolated from an airborne LIDAR survey. Surveys using Real-Time Kinematic Differential Global Positioning System (RTK-DGPS) instruments started in October 2004.

## Points of contact

- Creator (scientific and technical lead): Jonanthan Allan, DOGAMI, Jonathan.ALLAN@oregon.gov
- Publisher: NANOOS Data Manager, nanoos.dmac@gmail.com

## Projection and datum information

Spatial coordinates used in DOGAMI-NANOOS Oregon Beach and Shoreline Mapping Analysis Program datasets are encoded in one of two projections: NAD83 Oregon State Plane North ([EPSG:32126](http://epsg.io/32126)) or NAD83 Oregon State Plane South ([EPSG:32127](http://epsg.io/32127)). Easting and northing values are cartesian coordinates, with positive East and North. The vertical datum is referenced to the North American Vertical Datum of 1988 ([NAVD88](https://en.wikipedia.org/wiki/North_American_Vertical_Datum_of_1988)). All positional and elevation data are measured and provided in metric units (meters).

Coordinates in the Rockaway littoral cell dataset are encoded in NAD83 Oregon State Plane North projection, or EPSG code 32126 from the [EPSG Geodetic Parameter Dataset](https://en.wikipedia.org/wiki/EPSG_Geodetic_Parameter_Dataset).

## Dataset files

The Rockaway littoral cell contains 10 transects spanning the period 1997-10-18 to 2018-12-07. In addition to this README file, this dataset contains the following files:

1. Transect data files. 1 per transect, containing data from all surveys for the transect.
2. Littoral cell inventory files. One file in CSV format and one in GeoJSON, containing the same information.
3. FGDC metadata file. Transect metadata in XML format following the FGDC standard.

### 1. Transect data files

Data from all surveys conducted on a transect are stored in a single CSV file. Each row represents one survey point, and rows are ordered by survey date (earliest to latest) and survey point (start to end points, from land to the shore).

File names follow the following convention:

`Rockaway_Rck1_transect_data_prj_epsg32126.csv`

where `Rockaway` is the littoral cell short name, `Rck1` is the transect code (see the littoral cell inventory), and `32126` is the EPSG code for the projection used in the transect.

**Attribute descriptions:**

| Field | Description | Example
--------|-------------|--------
| survey_number | Incremental survey number starting from the first survey (1) | 1
| survey_date | Date survey was conducted | 1998-04-15
| point_number | Incremental survey-specific point number starting with 1 | 1
| easting_meters | NAD83 Oregon State Plane easting (meters) coordinate in the transect projection | 2230430.769
| northing_meters | NAD83 Oregon State Plane northing (meters) coordinate in the transect projection | 217674.658
| distance_meters | Horizontal distance in meters from the survey start point (0) | 0.000
| elevation_meters | Surface elevation (meters, NAVD88) | 6.763
| measurement_approach | Elevation and coordinate measurement approach (LIDAR or GPS) | LIDAR

### 2. Littoral cell inventory files

Summary information for each transect is compiled as a littoral cell inventory available in two formats: a tabular CSV file (`Rockaway_littoralcell_inventory.csv`) and a [GeoJSON](https://en.wikipedia.org/wiki/GeoJSON) file (`Rockaway_littoralcell_inventory.geojson`) depicting transect lines by connecting the start and end points (in latitude and longitude coordinates), which can be visualized and browsed using Geographical Information System (GIS) software. The two files contain the same information.

**Attribute descriptions:**

| Attribute | Description | Example
------------|-------------|--------
transect | Transect code used in file names | Rck1
littoralcell | Short littoral cell name used in file names | Rockaway
littoralcell_fullname | Complete littoral cell name | Rockaway
state | State where the transect is found | Oregon
provider | Dataset provider | DOGAMI-NANOOS
projection | State Plane projection used in the transect data easting and northing coordinates | epsg:32126
survey_count | Number of surveys carried out at this transect | 52
date_first | Date of first transect survey | 1998-04-15
date_last | Date of last transect survey | 2018-12-07
longitude | Longitude of transect median point | -123.9566
latitude | Latitude of transect median point | 45.574
start_lon | Longitude of transect start (first point) | -123.9549
start_lat | Latitude of transect start (first point) | 45.5736
end_lon | Longitude of transect start (end point) | -123.9593
end_lat | Latitude of transect start (end point) | 45.5746

Latitude and longitude WGS 84 ([EPSG:4326](http://epsg.io/4326)) coordinates are in decimal degrees. The following values are identical for all transects in this littoral cell dataset: littoralcell, littoralcell_fullname, state, provider and projection.

### 3. FGDC metadata file

Littoral cell metadata file in FGDC XML format.
