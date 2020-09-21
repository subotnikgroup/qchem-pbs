# QChem-PBS

QChem-PBS executes Q-Chem on a node via the scheduling system. It can replace `omniqchem.csh` and `node_local_qchem.csh` on venus, diabatical, and helium.


## Installation
Simply add `qchem-pbs` to your path, perhaps in `$HOME/bin`.


## Usage
Invocation is often as simple as:

```qchem-pbs myqcjob.in```

Which will schedule the job to be executed on a node in `$QCSCRATCH`, writing output to `myqcjob.out` with scratch files saved in `./run`.


See `qchem-pbs -h` for help and more options including threads for parallel jobs and selecting between Q-Chem branches (e.g.: you-dev-branch vs. trunk). 

## Contributing
Pull requests are welcome. Contact valecs@sas.upenn.edu if something seems broken.
