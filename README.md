# cluster_utils

#### Commonly used commands

```
squeue -u wpq

scancel -j <jobid>
scancel -n <jobname>

sinfo
sinfo --summarize
sinfo --node <nodename> --long

# Fix drained node
sinfo | grep drain
sudo scontrol update nodename=<nodename> state=idle
```

#### Utilities

- checks for driver version mismatch over nodes in cluster
    - When system updates driver version, the machines yield `Failed to initialize NVML: Driver/library version mismatch` error when executing `nvidia-smi`. This problem can be fixed with a system reboot. Instead of logging in to every machine to check if version mismatch happens, run the following commands to find out which machine has this problem.

```
cd check_gpu_available
make check_gpu
```


#### Info 

- cheatsheet: http://www.physik.uni-leipzig.de/wiki/files/slurm_summary.pdf
- slides explaining sbatch/slurm: https://www.cism.ucl.ac.be/Services/Formations/slurm/2016/slurm.pdf


#### Todo 


- a script that, when given a list of python 1-liner commands, submit all jobs 
    - a script that handles setting resource parameters, conda env
    - a list of python commands with potentially different arguments
