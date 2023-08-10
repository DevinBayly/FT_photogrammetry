## FT photogrammetry project
This project aims to assist students with reconstructing parts of the east range of Fort Huachuca. We will be using Open Drone Map and the UArizona HPC. This project is a proof of concept and due to the extreme amounts of space to capture certain workflow choices are being made that have implications for the quality of the final product.

### Contents

* batch_processing: this folder contains the scripts that are used to run the photogrammetry process on images that have been assigned to groups according to the qgis splitting workflow
* qgis_scripts: this folder provides scripts meant to be used in qgis to load images and section them into groups for processing 

### Containers required for this workflow

It is recommended that people interested in using these scripts first retrieve the Open Drone Map container, and convert it to a sandboxed singularity container so that it may be launched with `--writable` when necessary
```
singularity build --sandbox docker://opendronemap/odm:latest
```

Using the singularity container for qgis in a remote desktop environment will allow users to launch the gui from within the container.

```
singularity pull docker://ghcr.io/devinbayly/qgis_qt5
singularity exec qgis_qt5_latest.sif qgis
```


### Initial instructions for launching odm
getting allocation 
https://public.confluence.arizona.edu/display/UAHPC/Running+Jobs+with+SLURM
```
elgato 
interactive -a cdh -t 5:00:00 -N 1 -n 16  
```
```
cd /xdisk/bryancarter/
```
this brings you up a level in the directory 
```
cd ..
```

```
mv IMAGES images
```
using the singularity container from the HPC
```
cp ../baylyd/odm_latest.sif ./
```
singularity shell
puts us inside the container
```
singularity shell odm_latest.sif
```
run command to run the photogrammetry pipeline
```
python3 /code/run.py --project-path "WingtraPilotProjects/" "20230401 fth test1 Flight 01"
```


https://github.com/OpenDroneMap/ODM
