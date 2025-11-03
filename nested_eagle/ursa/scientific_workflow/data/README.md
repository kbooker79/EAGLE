## Workflow

Run `sbatch submit_grids.sh`
- This creates some static grid files that will be used for:
    - Regridding data later in the pipeline
    - Creation of grid for latent mesh during training
- Once this has completed you can move onto dataset creations.
- Notes if you plan to run multiple times or change things on your own:
    - This step creates static files that you can reuse, so if you run through this pipeline multiple times it may not be necessary to always re-run this.
    - In general, this script may not always be needed. It is only needed if you wish to regrid your data, or to create latent mesh if that is part of your model training.

Run `sbatch submit_gfs.sh` followed by `sbatch submit_hrrr.sh`
- You can run both of these at the same time. 
- One loads GFS data and the other loads HRRR data.
- Ideally, we will just submit these together in one job. However, we are currently restricted to 4 cores per job on Ursa at the moment, so this makes the whole process go a bit faster.

Note: Make sure that you update `#SBATCH --account=epic` within the slurm scripts to reflect your account.

Please see our [documentation](https://epic-eagle.readthedocs.io/en/latest/data_creation.html) for some quick tips and notes on this particular configuration if you wish to make any edits for testing.

For more in-depth information about ufs2arco capabilities, see the [ufs2arco documentation](https://ufs2arco.readthedocs.io/en/latest/)