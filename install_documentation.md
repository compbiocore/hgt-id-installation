## Getting the Files

The files needed to run HGT-ID are present on tdatasci in the following directory:

        /home/aleith/HGT-ID_v1.0
  
To copy these files to another location (e.g. on a different system), the `rsync` utility can be used.  For example, to copy the directory and its contents to `/users/aleith/scratch/hgt-id` on Oscar, the following command would be used:

        rsync -r -a -v -e ssh /home/aleith/HGT-ID_v1.0 [Oscar username]@ssh.ccv.brown.edu:[destination file path]
  
Note that the user will be required to substitute their own username and destination file path; a password prompt will occur when first running this command.  The `-v` option will cause the command to output each file as it is copied.

In addition to the HGT-ID files, this directory contains one additional file - a script: `/home/aleith/HGT-ID_v1.0/prepare_reference.sh`.
  
This script is used to prepare a reference for use with HGT-ID and is run by invoking:

        bash prepare_reference.sh [reference]
  
The UCSC version of hg19 is already prepared for use with the tool - for alternative references, this script should be run.

## Configuration

Once the files are copied to the destination server, it is necessary to modify the configuration file `config.txt` in the HGT-ID root directory.  Each file path in this file must be changed to point to the respective resources (generally by replacing `ROOT_PATH` with whatever the file path to the new HGT-ID root directory is).

Failing to modify every file path listed inside will result in errors.

A script to rapidly substitute a specific path into each entry exists in the HGT-ID root directory as `prepare_config.sh`, which can be run as follows:

        bash prepare_config.sh [HGT-ID root directory path]
