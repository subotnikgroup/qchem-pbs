# QChem-PBS

QChem-PBS executes Q-Chem on a node via the scheduling system. It can replace `omniqchem.csh` and `node_local_qchem.csh` on venus, diabatical, and helium.


## Installation
Download code with:

`git clone git@github.com:subotnikgroup/qchem-pbs.git`

Then add `qchem-pbs` to your path, perhaps in `$HOME/bin`.


## Usage
Invocation is often as simple as:

```qchem-pbs myqcjob.in```

Which will schedule the job to be executed on a node in `$QCSCRATCH`, writing output to `myqcjob.out` with scratch files saved in `./run`.

See `qchem-pbs -h` for help and more options including threads for parallel jobs and selecting memory limits.

### Branches
To easily switch between multiple Q-Chem branches (e.g.: my-dev-branch and trunk), pass the `--branch` option:

`qchem-pbs myqcjob.in --branch /path/to/my-dev-branch`

QChem-PBS will set `$QC` appropriately and execute the Q-Chem you compiled. If you set the environmental variable `$QCRT` (e.g. in bash.rc) and my-branch is a subdirectory of `$QCRT`, you can do the same with:

`qchem-pbs myqcjob.in -b my-dev-branch`

### Test your environment
The `--dry-run` option will check your Q-Chem environment and report errors:

```
qchem-pbs --dry-run test.in
...
Valid Q-Chem install not found at $QC!
$QCSCRATCH must be an absolute path!
Q-Chem requires that the variable QC_EXT_LIBS be set and exist!
Q-Chem requires that the variable QCAUX be set and exist!
Q-Chem requires that the variable QCPLATFORM be set!
...
```

## Contributing
Pull requests are welcome. Contact valecs@sas.upenn.edu if something seems broken.
