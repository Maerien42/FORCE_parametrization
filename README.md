# FORCE parametrization

## Create a harmonized Sentinel-2 and Landsat database

## Preparatory work
* Create DEM: https://force-eo.readthedocs.io/en/latest/howto/dem.html#
* Create vectorfile of study area (e.g. Shapefile or gpkg-file)
* Choose coordinate System (e.g. LAEA ETRS)


## Download data
/home/fegeo/member/stellmes/bin/force-level1-csd -c 0,50 -d 19880101,20051231 -s LT04,LT05,LE07 /home/fg-data/data-archive/catalogue /home/fg-data/data-archive/spain/download/ /home/fg-data/data-archive/spain/pool.txt /home/fg-data/data-archive/spain/geo/study_new.shp

