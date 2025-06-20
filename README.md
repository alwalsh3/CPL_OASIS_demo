# CPL OASIS demonstrator
Demonstrator for CPL OASIS NEMO test configuration.
Modifications needed to run the CPL_DEMONSTRATOR for NEMO5 

1.	New arch file for compilation (use it for both toyatm and nemo)
2.	XIOS3 compiled with OASIS support 
3.	OASIS
4.	Compile NEMO with key_xios AND key_xios3
5.	Iodef update oasis_codes_id  clients_code_id
6.	Job script updated for your own HPC architecture. 
Slurm or PBC. Sometimes we have to mess around the order of executables called. For some architecture call nemo, xios and toyatm (in this order) for some other xios is called last. 

We need to get the ORCA2 files from     wget "https://gws-access.jasmin.ac.uk/public/nemo/sette_inputs/r5.0.0/ORCA2_ICE_v5.0.0.tar.gz"


## Getting started
### Prerequisits

You will need to have an installation of OASIS3-MCT, and a version of XIOS3 which has been compiled for OASIS. 

To compile XIOS3 for use with OASIS, do 

```
./make_xios --prod --use_oasis oasis3_mct --arch your_Arch_file --full --job 8
```

## Install NEMO

This demonstrator is for NEMO v5.0.1.

To install this version, do 

```
git clone --branch 5.0.1 https://forge.nemo-ocean.eu/nemo/nemo.git nemo_5.0.1
```


