# GNSS_processing
These scripts help the automation of zenith wet delay (zwd) or zenith total delay (ztd) calculation from GNSS raw files (.ubx or something).\
We employ RTKLIB (https://github.com/tomojitakasu/RTKLIB/tree/rtklib_2.4.3) and CSRS-PPP (https://webapp.csrs-scrs.nrcan-rncan.gc.ca/geod/tools-outils/ppp.php) for obs file conversions and zwd calculations, respectively.

## ubx_to_obs.ipynb
We use convbin app from RTKLIB.
Clone https://github.com/tomojitakasu/RTKLIB/tree/rtklib_2.4.3 and run \
`$ RTKLIB/app/convbin/gcc make`.

This notebook runs the following process:
1. Decompress the ubx files
2. Convert ubx files to obs files using convbin
3. Compress the obs files.

## PPPdirect_run.ipynb
We use "PPP direct", windows desktop app for CSRS-PPP, which can be downloaded from Canadian gorverment website (https://www.canada.ca/en.html).
The download page locates at
`Canada.ca > Natural Resources Canada > Maps, Tools and Publications > Geodetic Reference Systems > Geodetic tools and data > Desktop Applications`.\
This app enables the automation of downloading the CSRS-PPP result files to your local folder.

After the installation of PPP direct app, PPP direct.lnk will be created on your desktop. \
Opening the app, you can change the configuration of csrs-ppp.\
The official instruction says that 
> PPPdirect lets the user "drag and drop" RINEX files onto a desktop icon where they are immediately submitted for CSRS-PPP processing.

This notebook operates it by the script.\
I would like to note that pppdirect_path must be .lnk file on your desktop, not .exe in the Program Files. Otherwise the script doesn't work.

## read_tro_database.ipynb
This script reads the zwd from CSRS-PPP outputs.
