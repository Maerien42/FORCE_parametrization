# FORCE parametrization

## Create a harmonized Sentinel-2 and Landsat database

Disclaimer 1: Examples are mixed between several study areas

Disclaimer 2. The uploaded paramterfiles might be slightly outdated, please compare them with the newest version.

## Preparatory work
* Create DEM:
* Create vectorfile of study area (e.g. Shapefile), best option to use geographic coordinates (EPSG: 4326)
* Choose coordinate System (e.g. LAEA ETRS) for output

## SRTM
Follow the intro here:  https://force-eo.readthedocs.io/en/latest/howto/dem.html#
    
    * Download tiles
    * build text file containing list of images
    * gdalbuildvrt -input_file_list srtm.txt srtm.vrt
   
    
## Create Landsat database

### Configure login to GEE and download data catalogue
Follow the intro here: https://force-eo.readthedocs.io/en/latest/howto/level1-csd.html#tut-l1csd

    force-level1-csd -u /ZEDAT/fegeo/data-archive/catalogue/
    
    
### Download data
Even if you only want to work with Sentinel 2 data: If you would like to use geocorrection you also need Landsat 8 data. 
These need to cover the spatial extent of the to-be-coregistered Sentinel-2 images. 
    
    force-level1-csd -c 0,50 -d 20150101,20221231 -s LC08 /home/fg-data/data-archive/catalogue /home/fg-data/data-archive/spain/download/ /home/fg-data/data-archive/spain/pool.txt /home/fg-data/data-archive/spain/geo/study_new.shp


### Create parameter file for processing Landsat level2 data
Follow the intro here: https://force-eo.readthedocs.io/en/latest/components/auxilliary/parameter.html

    force-parameter /data/force/param/l2ps.prm LEVEL2
    
Example can be found in ``prm`` folder
    
### Run level-2 module


### Create tile list


### Creating the base images
The base images can be readily generated using the Time Series Analysis (TSA) submodule of the FORCE Higher Level Processing system (HLPS).

Example parameter file can be found in ``prm`` folder


### Create coregistered Sentinel level 2 data

Example parameter file can be found in ``prm`` folder

