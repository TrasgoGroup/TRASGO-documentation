# TRAGALDABAS-documentation

Directories in this repository:

## ExternalHDDs_directories/

Here there is a file for each external hard disk, where we represent their detailed tree-directories. Also there is a folder-template called `tree_dir_template/` with the `latex_file.tex` to document new hard disks and a script called `create_tree` to create the default tree directory.

### How to use the script `create_tree`?

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


## documentation/
General documentation in pdf.

