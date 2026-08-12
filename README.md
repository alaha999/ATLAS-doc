# ATLAS-doc
Docs related to ATLAS work

List of Content:
- Search Datasets
- Rucio Command Quick Guide

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

# Rucio Command Quick Guide

This guide provides a short reference for commonly used **Rucio commands** in ATLAS, with examples based on the dataset:

```text
mc23_13p6TeV.546587.MGPy8EG_lv_offsh_mZp_500_ee.deriv.DAOD_PHYS.e8588_a934_r16083_p6697
```

For this dataset, the scope is:

```text
mc23_13p6TeV
```

and the full Rucio DID is:

```text
mc23_13p6TeV:mc23_13p6TeV.546587.MGPy8EG_lv_offsh_mZp_500_ee.deriv.DAOD_PHYS.e8588_a934_r16083_p6697
```
### Quick reference

| Task                     | Command                                           |
| ------------------------ | ------------------------------------------------- |
| Check Rucio connection   | `rucio ping`                                      |
| Check current user       | `rucio whoami`                                    |
| List user scopes         | `rucio list-scopes`                               |
| Search datasets          | `rucio list-dids "<scope>:<pattern>"`             |
| List files in dataset    | `rucio list-files "<scope>:<dataset>"`            |
| List container contents  | `rucio list-content "<scope>:<container>"`        |
| Show dataset locations   | `rucio list-dataset-replicas "<scope>:<dataset>"` |
| Show file locations      | `rucio list-file-replicas "<scope>:<dataset>"`    |
| Download dataset         | `rucio download "<scope>:<dataset>"`              |
| Download one random file | `rucio download --nrandom 1 "<scope>:<dataset>"`  |

---

## 1. Basic Rucio checks

Setup rucio
```bash
<login to lxplus>
cd $WORKDIR
voms-proxy-init -voms atlas
setupATLAS
lsetup rucio
```

Check whether Rucio can communicate with the server:

```bash
rucio ping
```

Example output:

```text
OK
```

Check your current Rucio identity:

```bash
rucio whoami
```

This shows information such as your Rucio account and authentication details.

---

## 2. Rucio nomenclature

Rucio identifies objects using a **Data Identifier (DID)** with the form:

```text
<scope>:<name>
```

For example:

```text
mc23_13p6TeV:mc23_13p6TeV.546587.MGPy8EG_lv_offsh_mZp_500_ee.deriv.DAOD_PHYS.e8588_a934_r16083_p6697
```

Here:

```text
scope = mc23_13p6TeV
```

and:

```text
name = mc23_13p6TeV.546587.MGPy8EG_lv_offsh_mZp_500_ee.deriv.DAOD_PHYS.e8588_a934_r16083_p6697
```

---

## 3. List your user scopes

To find scopes associated with your user account:

```bash
rucio list-scopes | grep "$USER"
```

For example, if your username is `alaha`, you may see:

```text
user.alaha
```

Your personal Rucio scope is normally:

```text
user.<username>
```

For example:

```text
user.alaha
```

---

## 4. List datasets in your user scope

To list DIDs in your user scope:

```bash
rucio list-dids "user.${USER}:*"
```

For example:

```bash
rucio list-dids "user.alaha:*"
```

This can return user datasets such as:

```text
user.alaha:user.alaha.myAnalysisSample
user.alaha:user.alaha.testOutput
```

---

## 5. Search for a dataset

You can search for datasets using wildcards.

For example, to look for the sample with DSID `546587`:

```bash
rucio list-dids "mc23_13p6TeV:*546587*"
```

A more specific search could be:

```bash
rucio list-dids "mc23_13p6TeV:*MGPy8EG_lv_offsh_mZp_500_ee*"
```

To search directly for the full dataset name:

```bash
rucio list-dids "mc23_13p6TeV:mc23_13p6TeV.546587.MGPy8EG_lv_offsh_mZp_500_ee.deriv.DAOD_PHYS.e8588_a934_r16083_p6697"
```

You can also search broadly for DAOD_PHYS datasets:

```bash
rucio list-dids "mc23_13p6TeV:*546587*DAOD_PHYS*"
```

---

## 6. List files inside a dataset

To see all files belonging to a dataset:

```bash
rucio list-files \
"mc23_13p6TeV:mc23_13p6TeV.546587.MGPy8EG_lv_offsh_mZp_500_ee.deriv.DAOD_PHYS.e8588_a934_r16083_p6697"
```

The output contains information such as:

```text
$ rucio list-files mc23_13p6TeV.546587.MGPy8EG_lv_offsh_mZp_500_ee.deriv.DAOD_PHYS.e8588_a934_r16083_p6697
+-----------------------------------------------------+--------------------------------------+-------------+------------+----------+
| SCOPE:NAME                                          | GUID                                 | ADLER32     | FILESIZE   | EVENTS   |
|-----------------------------------------------------+--------------------------------------+-------------+------------+----------|
| mc23_13p6TeV:DAOD_PHYS.45529190._000001.pool.root.1 | E18B85D0-8D4B-E047-87F5-8D6C02F9DC3D | ad:d69d23ef | 293.840 MB | 10000    |
| mc23_13p6TeV:DAOD_PHYS.45529190._000002.pool.root.1 | F3E5AA53-A665-5E45-BE7B-7749210C44B4 | ad:e7bc0c5b | 576.914 MB | 20000    |
+-----------------------------------------------------+--------------------------------------+-------------+------------+----------+
Total files : 2
Total size : 870.754 MB
Total events : 30000
```

This is useful for checking:

* number of files,
* individual file names,
* file sizes,
* checksums.

---

## 7. List the contents of a container

A Rucio **container** can contain one or more datasets.

To list its contents:

```bash
rucio list-content <scope>:<container-name>
```

For example, suppose a container is called:

```text
mc23_13p6TeV:mc23_13p6TeV.546587.MGPy8EG_lv_offsh_mZp_500_ee.deriv.DAOD_PHYS.e8588_a934_r16083_p6697
```

then:

```bash
rucio list-content \
"mc23_13p6TeV:mc23_13p6TeV.546587.MGPy8EG_lv_offsh_mZp_500_ee.deriv.DAOD_PHYS.e8588_a934_r16083_p6697"
```

If the DID is a container, this displays the datasets contained inside it.

If it is already a dataset rather than a container, use:

```bash
rucio list-files <scope>:<dataset>
```

instead.

---

## 8. Find where a dataset is stored

To find the Rucio Storage Elements (RSEs) containing replicas of a dataset:

```bash
rucio list-dataset-replicas \
"mc23_13p6TeV:mc23_13p6TeV.546587.MGPy8EG_lv_offsh_mZp_500_ee.deriv.DAOD_PHYS.e8588_a934_r16083_p6697"
```

Example output may contain sites such as:

```text
CERN-PROD_DATADISK
UKI-LT2-QMUL_DATADISK
INFN-ROMA1_DATADISK
```

along with information about the number of available files.

This is useful for checking whether the entire dataset exists at a particular site.

---

## 9. Find locations of individual files

To see replica locations at the file level:

```bash
rucio list-file-replicas \
"mc23_13p6TeV:mc23_13p6TeV.546587.MGPy8EG_lv_offsh_mZp_500_ee.deriv.DAOD_PHYS.e8588_a934_r16083_p6697"
```

This shows where individual files are physically available.

This is useful when:

* debugging missing files,
* checking specific storage sites,
* finding PFNs,
* investigating incomplete dataset replicas.

---

## 10. Download the complete dataset

To download all files in the dataset:

```bash
rucio download \
"mc23_13p6TeV:mc23_13p6TeV.546587.MGPy8EG_lv_offsh_mZp_500_ee.deriv.DAOD_PHYS.e8588_a934_r16083_p6697"
```

Rucio will create a directory and download the available files into it.

---

## 11. Download only one random file

For a large dataset, it is often useful to download just one file for testing.

Use:

```bash
rucio download --nrandom 1 \
"mc23_13p6TeV:mc23_13p6TeV.546587.MGPy8EG_lv_offsh_mZp_500_ee.deriv.DAOD_PHYS.e8588_a934_r16083_p6697"
```

This downloads one randomly selected file from the dataset.

This is particularly useful for:

* testing analysis code,
* inspecting branches,
* checking metadata,
* validating ROOT files before processing the complete dataset.

---

## 12. Download several random files

The same option can be used to download more than one file.

For example, download three random files:

```bash
rucio download --nrandom 3 \
"mc23_13p6TeV:mc23_13p6TeV.546587.MGPy8EG_lv_offsh_mZp_500_ee.deriv.DAOD_PHYS.e8588_a934_r16083_p6697"
```

---



