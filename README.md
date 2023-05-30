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
cp ../baylyd/odm_latest.sif ./https://public.confluence.arizona.edu/display/UAHPC/Running+Jobs+with+SLURM
```


```
singularity shell

```
