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

