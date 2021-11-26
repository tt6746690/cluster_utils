# cluster_utils

#### Commonly used commands

```
squeue -u wpq
sinfo
scancel -j <jobid>
scancel -n <jobname>
```

##### Fix drained node

```
sinfo | grep drain
sudo scontrol update nodename=<nodename> state=idle
```


#### info 

- slides explaining sbatch/slurm https://www.cism.ucl.ac.be/Services/Formations/slurm/2016/slurm.pdf


#### todo 


- a script that checks nvidia-smi works and version of gpu driver over cluster
    - not use any gpu resource
    - output {node: node_gpu_info} to a file for inspection
- a script that, when given a list of python 1-liner commands, submit all jobs 
    - a script that handles setting resource parameters, 
    - 