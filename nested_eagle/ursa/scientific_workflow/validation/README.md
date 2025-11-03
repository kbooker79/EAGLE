## Workflow

#### Step 1:
First, we must post-process Anemoi output to ensure it is compatible with wxvx. To do this, run: 
`sbatch submit_postprocessing.sh`

#### Step 2:
After post-processing is complete, run:
`sbatch submit_validation.sh`

Note: Make sure that you update `#SBATCH --account=epic` within the slurm scripts to reflect your account.

Now go to `run/plots/` and open some plots showing RMSE and ME for various variables. 
