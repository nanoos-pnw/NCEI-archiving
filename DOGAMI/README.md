# README

- Draft README file for archive files: [README_Archive.md](https://github.com/nanoos-pnw/NCEI-archiving/blob/master/DOGAMI/README_Archive.md)
- See sample files at http://data.nanoos.org/ncei/dogami/
- Littoral Cells in initial archiving batch: Bayocean, Nehalem, Neskowin, Rockaway
- [Littoral Cell inventory sample on GitHub](https://github.com/nanoos-pnw/NCEI-archiving/blob/master/DOGAMI/Bayocean_littoralcell_inventory.geojson); GeoJSON files on GitHub are rendered on an interactive, Google-Maps-type map
- Sample NANOOS (OHSU-CMOP/CRITFC) dataset archived at NCEI: https://data.nodc.noaa.gov/cgi-bin/iso?id=gov.noaa.nodc:0161524

## Package structure
```
+---Bayocean
|   |   bag-info.txt
|   |   bagit.txt
|   |   manifest-sha256.txt
|   |   tagmanifest-sha256.txt
|   |
|   \---data
|           Bayocean_Bay1_transect_data_prj_epsg32126.csv
|           Bayocean_Bay2_transect_data_prj_epsg32126.csv
|           Bayocean_Bay3_transect_data_prj_epsg32126.csv
|           Bayocean_Bay4_transect_data_prj_epsg32126.csv
|           Bayocean_Bay5_transect_data_prj_epsg32126.csv
|           Bayocean_Bay6_transect_data_prj_epsg32126.csv
|           Bayocean_Bay7_transect_data_prj_epsg32126.csv
|           Bayocean_FGDC_Metadata.xml
|           Bayocean_littoralcell_inventory.csv
|           Bayocean_littoralcell_inventory.geojson
|           README.md
|
+---Nehalem
|   |   bag-info.txt
|   |   bagit.txt
|   |   manifest-sha256.txt
|   |   tagmanifest-sha256.txt
|   |
|   \---data
|           Nehalem_FGDC_Metadata.xml
|           Nehalem_littoralcell_inventory.csv
|           Nehalem_littoralcell_inventory.geojson
|           Nehalem_Neh1_transect_data_prj_epsg32126.csv
|           Nehalem_Neh2_transect_data_prj_epsg32126.csv
|           Nehalem_Neh3_transect_data_prj_epsg32126.csv
|           Nehalem_Neh4_transect_data_prj_epsg32126.csv
|           Nehalem_Neh5_transect_data_prj_epsg32126.csv
|           Nehalem_Neh6_transect_data_prj_epsg32126.csv
|           Nehalem_Neh7_transect_data_prj_epsg32126.csv
|           Nehalem_Neh8_transect_data_prj_epsg32126.csv
|           README.md
|
+---Neskowin
|   |   bag-info.txt
|   |   bagit.txt
|   |   manifest-sha256.txt
|   |   tagmanifest-sha256.txt
|   |
|   \---data
|           Neskowin_FGDC_Metadata.xml
|           Neskowin_littoralcell_inventory.csv
|           Neskowin_littoralcell_inventory.geojson
|           Neskowin_Nesk10_transect_data_prj_epsg32126.csv
|           Neskowin_Nesk11_transect_data_prj_epsg32126.csv
|           Neskowin_Nesk12_transect_data_prj_epsg32126.csv
|           Neskowin_Nesk13_transect_data_prj_epsg32126.csv
|           Neskowin_Nesk14_transect_data_prj_epsg32126.csv
|           Neskowin_Nesk15_transect_data_prj_epsg32126.csv
|           Neskowin_Nesk1_transect_data_prj_epsg32126.csv
|           Neskowin_Nesk2_transect_data_prj_epsg32126.csv
|           Neskowin_Nesk3_transect_data_prj_epsg32126.csv
|           Neskowin_Nesk4_transect_data_prj_epsg32126.csv
|           Neskowin_Nesk5_transect_data_prj_epsg32126.csv
|           Neskowin_Nesk6_transect_data_prj_epsg32126.csv
|           Neskowin_Nesk7_transect_data_prj_epsg32126.csv
|           Neskowin_Nesk8_transect_data_prj_epsg32126.csv
|           Neskowin_Nesk9_transect_data_prj_epsg32126.csv
|           README.md
|
\---Rockaway
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

## Package sizes
| Package | Size |
----------|-------
| Bayocean | 5.2M |
| Nehalem | 6.2M |
| Neskowin | 7.2M |   
| Rockaway | 5.7M |
