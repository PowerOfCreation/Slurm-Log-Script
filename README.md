# Introduction

This script gives you useful information like reserved memory, partition name or system name each time you start a slurm job as long as the sbatch script has this debug.sh shellscript included.

# Copyright

Most of this code has been written by Norman Koch working at the TU Dresden. He has put this under the WTFPL License and gave it to me. I made minor changes and decided to put this repository under a MIT license.

# Usage

Include the debug.sh shellscript in your sbatch script using source:

start.sbatch:
```bash
#!/bin/bash

#SBATCH --mem=4GB
#SBATCH -c 1
#SBATCH --time=01:00:00
#SBATCH --nodes=1

source debug.sh

srun python example.py
print_time # Optional
```

Exeuction
```
sbatch start.sbatch
```
