## Workflow

Run the following to submit a job to create a 10-day forecast:

`sbatch submit_inference.sh`

Note: Make sure that you update `#SBATCH --account=epic` within the slurm scripts to reflect your account.

This script will use `eagle-tools` to execute `anemoi-inference`. Your forecast files will be saved as NetCDF's in a `inference_files` directory.

Note
- Within `inference_config.yaml` you will find a path to a checkpoint. The submit script updates that for you. However, if you have trained multiple models (due to testing things, something failed the first time, etc.) you may have to go edit the checkpoint path yourself to find the specific run_id you wish to use a checkpoint from. If you do this, then go comment out the first 2 lines of the submit_inference.sh script as well.
