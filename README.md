## FT photogrammetry project

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
