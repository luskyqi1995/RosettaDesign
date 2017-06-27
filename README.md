# RosettaDesign
RosettaDesign using PyRosetta

## Decription
This is a python script that allows fixed backbone (fixbb) design of a protein using PyRosetta. It has two functions:
1. Design_Whole(): Design the whole protein all the onces.
2. Design_Layer(): Designs each protein layer (core, boundry, surface) seperatly. This is the default setting because it is faster and seems to be more accuate (futher testing needed).
3. This script has only been tested in GNU/Linux.
4. The script has the following sequence:

    * Relax structure
    * Identify layers
    * Design core
    * Design boundary
    * Design surface
    * Relax structure
    * Repeat three times steps 2-6
    * Output final designed structure

## Requirements
1. You will require DSSP to identify the different protein layers, install using the following command:

`sudo apt install DSSP`

2. You will also need some python libraries that are used within the script, install them using the following commands:

    * If you do not have pip that installs python libraries, install it using this command:
    
    `sudo apt install python3-pip`

    * Install the python libraries
    
    `sudo python3 -m pip install numpy biopython`

## How to use
1. This script and the desired structure to design (FILENAME.pdb) should be in the same working directory.
2. The .pdb file should be cleaned for Rosetta.
3. Run using the following command:

`python3 RosettaDesign.py FILENAME.pdb`

4. The computation takes around 20-60 minutes depending on the protein's size.
5. The script outputs only the final designed .pdb structure.
6. Use Rosetta Abinitio to predict the fold of this new design.