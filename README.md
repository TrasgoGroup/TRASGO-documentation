# TRASGO-documentation

Central repository with [*TrasgoGroup*](https://github.com/TrasgoGroup) Documentation. Check [PDF Here](documentation/main.pdf).

## Software repositories

Here are all the links to code repositories useful for simulation, analysis and slowcontrol in the *TrasgoGroup*. All of them have their own documentation in the `README.md` (main page of each repository).

- [Cellmap Viewer](https://github.com/TrasgoGroup/Cell-Viewer): Graphical User Interface to monitor data from TRASGO type detectors.
- [Tragaldabas alarm](https://github.com/TrasgoGroup/TRAGALDABAS-alarm): When the system is not saving data in the corresponding directory for whatever reason, it is expected to receive a message to the Telegram bot called ***TRAGALDABAS-alarms*** (*@tragaldabas_bot*).
- [TRUFA](https://github.com/TrasgoGroup/TRUFA): Unpacking and tracking code for Tragaldabas (TRasgo User-friendly Framework for Analysis).
- [EnsarRoot](https://github.com/TrasgoGroup/EnsarRoot): EnsarRoot, the framework for simulation and data analysis for ENSAR.
- [Tristan Aires Simulation](https://github.com/TrasgoGroup/TRISTAN-journey-simulation): Simulation of particle showers on the TRISTAN detector on its journey through the Atlantic Ocean.
- [Tristan Data Reader](https://github.com/TrasgoGroup/TRISTAN-hesperides-reader): Reading data from Tristan on Hesperides.
- [Kalman FIlter](https://github.com/MCruces-fz/TRAGALDABAS-Kalman-Filter): Genedigitana using Kalman Filter for reconstruction with Tragaldabas.
- [Entries and Multiplicity Analysis for Tragaldabas](https://github.com/MCruces-fz/STRATOS): Codes written for STRATOS collaboration (USC) by Martina Feijoo.

Thanks to anyone who continues to add documented repositories.

Peace :v:

## Directories in this repository

### documentation/
General documentation in [pdf](documentation/main.pdf).

### ExternalHDDs_directories/

Here there is a file for each external hard disk, where we represent their detailed tree-directories. Also there is a folder-template called `tree_dir_template/` with the `latex_file.tex` to document new hard disks and a script called `create_tree` to create the default tree directory.

#### How to use the script `create_tree`?

Of course, it works only for Linux systems. To see the help, type
```bash
./create_tree --help
```
it will show this:
```bash
Usages:
source create_tree make <detector_name>
./create_tree make <detector_name>
```

You can edit the function `create_tree()`, which only uses `mkdir -p` command:
```bash
function create_tree() {
    echo "Creating tree of directories for $DETECTOR detector..."

    mkdir -vp $DETECTOR/data/raw/
    mkdir -vp $DETECTOR/data/dst/

    ...
}
```
to make your own custom directory-tree.

