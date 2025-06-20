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


## Getting started
### Prerequisites

You will need to have an installation of OASIS3-MCT, and a version of XIOS3 which has been compiled for OASIS. 

To compile XIOS3 for use with OASIS, do 

```
./make_xios --prod --use_oasis oasis3_mct --arch your_Arch_file --full --job 8
```

## Download and compile NEMO

This demonstrator is for NEMO v5.0.1.

To install this version, do 

```
git clone --branch 5.0.1 https://forge.nemo-ocean.eu/nemo/nemo.git nemo_5.0.1
```
### Clone this Demonstrator repository
This demonstrator includes an updated version of the CPL_OASIS test case, so next we will need to clone the repository.

```
git clone https://github.com/alwalsh3/CPL_OASIS_demo.git
```

### Copy new CPL_OASIS and compile
Navigate to the location of the test coniguration CPL_OASIS:

```
cd /nemo_5.0.1/tests/
```
Then, from the clone of this repository that you have made, copy the CPL_OASIS directory to `/nemo_5.0.1/tests/` (overwriting the version there by default).

We are now ready to compile the CPL_OASIS test case. To do this, navigate to the NEMO home directory `/nemo_5.0.1/` (the one which contains `makenemo`), and run the command

```
./makenemo -a CPL_OASIS -n MYCPL_OASIS -m your_Arch_file -j 8
```


## Download forcing data
We need to get the ORCA2 ancilliary files which can be downloaded from here:

```
wget "https://gws-access.jasmin.ac.uk/public/nemo/sette_inputs/r5.0.0/ORCA2_ICE_v5.0.0.tar.gz"
```




