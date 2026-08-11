# ATLAS-doc
Docs related to ATLAS work

# Search Datasets
- Setup pyAMI
```bash
setupATLAS
lsetup pyami
voms-proxy-init -voms atlas:/atlas
```

- Query datasets
```bash
# Find every dataset for DSID 561322
ami list datasets "mc23_13p6TeV.561322.%"

# Only mc23d
ami list datasets "mc23_13p6TeV.561322.%" | grep mc23d

# DAOD_LLP1 datasets
ami list datasets "mc23_13p6TeV.561322.%.DAOD_LLP1.%"

# Search for a sample name
ami list datasets "mc23_13p6TeV.%.%Tchan2EJs%"

# Search data
ami list datasets "data23_13p6TeV.%.physics_Main.%.DAOD_LLP1.%"
```

- Inspect one exact dataset in more detail

```bash
ami show dataset info mc23_13p6TeV.601230.PhPy8EG_A14_ttbar_hdamp258p75_dil.deriv.DAOD_PHYSLITE.e8514_s4159_r15530_pXXXX
```
- dataset provenance—i.e. the chain of parent/input/output datasets.

```bash
ami show dataset prov mc23_13p6TeV.561322.SomeSignal.deriv.DAOD_LLP1.eXXXX_sXXXX_rXXXX_pXXXX
```

- Getting only particular fields

```bash
ami list datasets \
    --fields logicalDatasetName,datasetNumber,events,crossSection \
    "mc23_13p6TeV.601230.%"
```
