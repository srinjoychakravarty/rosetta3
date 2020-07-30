This example shows a possible usage of the rosetta software on the cluster.
Follow the instructions below to run in:
1. Copy the directory to your local _scratch_ directory, since it his the **highest-performing** _read/write_ partition available to you:
```bash
$ cp -r /shared/centos7/rosetta/usage_examples/rosetta_score /scratch/$USER
```
2. Change into your local scratch directory
```bash
$ cd /scratch/$USER
```
3. The shell script **submit.bash** loads the _rosetta module_ and runs the scoring program _score_jd2.static_ using the _linuxgccrelease_ binary on the protein data bank(.pdb) file: _3TDM.pdb_. It saves any errors from the executed code in _test.err_ and any successful output in _test.out_

4. Submit your job to the universal SLURM job scheduler queue by typing: 
```bash
$ sbatch submit.bash
```
Your job will be automatically picked up and processed soon enough.

5. Check your job status by typing: 
```bash
$ squeue -u $USER
```

6. When the job is done, you should see an empty error file test.err and a full output file: test.out of what was printed "to the $
Additional files may have also been created, depending on the rosetta program being used.

7. Modifying the script to use other rosetta programs:

All of the programs (program list) are available at the location: **/shared/centos7/rosetta/2020.08.61146/main/source/bin**

By loading the rosetta module, they all are available for use in your script.

8. The script is set up to run on the express partition for **up to an hour** (should require much less than that), but you can customise that by refering to our [documentation](https://rc-docs.northeastern.edu/en/latest/using-discovery/slurmexamples.html#sbatch-examples).

Please follow the [Rosetta Getting Started Guide](https://www.rosettacommons.org/docs/latest/getting_started/Getting-Started) for more info about the different programs.
