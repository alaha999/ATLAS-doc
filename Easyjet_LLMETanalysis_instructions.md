# Setup easyjet framework for Dilepton + MET analysis

Here are the step by step instructions to run easyjet framework to produce ntuples from DAOD-PHYS samples.

- Easyjet repo: https://gitlab.cern.ch/easyjet/easyjet
- Alessio's repo with LLMET config: https://gitlab.cern.ch/atlas-phys/exot/lpx/exot-2023-28/easyjet_leptonsmet/-/tree/alpizzin-master-patch-87270/LeptonsMETAnalysis?ref_type=heads

*Step 0: Fork the easyjet repo in your `gitlab.cern namespace` (Example forked repo: https://gitlab.cern.ch/alaha/easyjet)*

Once done, follow these instructions once you login into your lxplus work area

```bash
<login to your lxplus>
cd <work-area>
mkdir my-analysis
cd my-analysis

#checking out easyjet repo
setupATLAS
lsetup git
git lfs install #IMPORTANT: needed to pull LFS files; only needs to be setup once
# Copy-paste this repo's URL, choosing your preferred authentication scheme, e.g. for lxplus or institute cluster
git clone --recursive --no-checkout --origin upstream ssh://git@gitlab.cern.ch:7999/easyjet/easyjet.git
cd easyjet
git sparse-checkout init --cone
git sparse-checkout set EasyjetHub EasyjetTests YourFavouriteAnalysis #use `ExampleAnalysis` for now
git checkout upstream/main
git submodule update --init --recursive

#set your forked branch as remote repo with an alias named origin and fetch it:
git remote add origin ssh://git@gitlab.cern.ch:7999/$(git config user.name)/easyjet.git
git fetch origin
```

Now everything should be up-to-date to your forked repo. Let's do some due diligences using git. 
```
#execute the following command
$ git branch

#output
* (HEAD detached at upstream/main)
  main

# So, we are at upstream/main branch. let's create a branch which we will use for development
$ git switch -c dilepton-analysis-dev upstream/main
$ git status

#output
On branch dilepton-analysis-dev

#That's great! Now we can track our dev work using this branch
# Also now you will have two remote gitlab repo connected

$ git remote -v

#output
origin    ssh://git@gitlab.cern.ch:7999/alaha/easyjet.git      #should be used to push code in your FORKED repo
upstream  ssh://git@gitlab.cern.ch:7999/easyjet/easyjet.git    #to push codes in official easyjet repo (not needed generally)

#how to push changes and dev work (assuming you did the git add and git commit)
git push -u origin my-analysis-dev  [git push -u <remote-repo-alias> <current-branch-name>]

```


If you don't have the dilepton+MET analysis config files and a few other necessary files needed for easyjet framework to run, do the following:

```
cd easyjet
mkdir LLMETanalysis
cd LLMETanalysis
mkdir datasets share
cd ..

#you need to get a few files from my public area or alternatively check the below repo
#https://gitlab.cern.ch/atlas-phys/exot/lpx/exot-2023-28/easyjet_leptonsmet/-/tree/alpizzin-master-patch-87270/LeptonsMETAnalysis?ref_type=heads
#you need to have the same structure

#To let know the build about the directory structure, libraries and all
cp /afs/cern.ch/work/a/alaha/public/ATLAS/HiggsDilepAnalysis/easyjet/LLMETanalysis/CMakeLists.txt .

#copy datasets-text files needed to submit grid-jobs
cp -r /afs/cern.ch/work/a/alaha/public/ATLAS/HiggsDilepAnalysis/easyjet/LLMETanalysis/datasets/* datasets/

#copy easyjet-run-config for dilepton+MET analysis
cp -r /afs/cern.ch/work/a/alaha/public/ATLAS/HiggsDilepAnalysis/easyjet/LLMETanalysis/share/* share/
```
Inside easyjet directory you should have the following structure of LLMETanalysis:
```text
$ tree LLMETanalysis/
LLMETanalysis/
├── CMakeLists.txt
├── datasets
│   ├── mc_Zprime_1000GeV_test.txt
│   └── mc_Zprime_allMasses_DAOD_PHYS.txt
└── share
    ├── RunConfig-LeptonsMET.yaml
    └── trigger.yaml
```


**Now time to build easyjet in order to run it to produce ntuples from DAOD-PHYS samples.**

```bash
cd my-analysis #(This is the base work area where you will see easyjet/ directory)
mkdir build run
cd build
source ../easyjet/setup.sh
cmake ../easyjet/
make
source */setup.sh
cd ..
mkdir run
cd run
# Launch your favorite easyjet command
easyjet-ntupler -c LLMETanalysis/RunConfig-LeptonsMET.yaml -o outputtest_easyjetntuple.root </path/to/input DAOD-PHYS-files>
```
You should get an output root file with the name: `outputtest_easyjetntuple.root`. This should have many branches. Look at them and they should look familiar.



### Submit locally on lxplus
```bash
easyjet-ntupler -c LLMETanalysis/RunConfig-LeptonsMET.yaml -o output_easyjetntuple.root /eos/user/a/alaha/HiggsDilepAnalysis/mc23_13p6TeV.546587.MGPy8EG_lv_offsh_mZp_500_ee.deriv.DAOD_PHYS.e8588_a934_r16083_p6697/DAOD_PHYS.45529190._000002.pool.root.1
```

### Submit grid-jobs

```bash
[alaha@lxplus914 run]$ easyjet-gridsubmit --mc-list ../easyjet/LLMETanalysis/datasets/mc_Zprime_1000GeV_test.txt --run-config LLMETanalysis/RunConfig-LeptonsMET.yaml --campaign testmc23e --noTag --noEmail
```
output:

```text
INFO : archiving source files with cpack
INFO : the build directory is /afs/cern.ch/work/a/alaha/public/ATLAS/HiggsDilepAnalysis/build
INFO : archiving source files
INFO : archiving InstallArea
INFO : gathering files under /afs/cern.ch/work/a/alaha/public/ATLAS/HiggsDilepAnalysis/run/./
  skip root file ./output_easyjetntuple.root
INFO : please use --extFile if you need to send the skipped files to WNs
INFO : checking sandbox
prun --inDS mc23_13p6TeV.546597.MGPy8EG_lv_offsh_mZp_1000_ee.deriv.DAOD_PHYS.e8588_a934_r16083_p6697 --outDS user.alaha.testmc23e.2026_08_12_T173338.546597.e8588_a934_r16083_p6697 --exec easyjet-ntupler %IN -l --run-config config.yaml --out-file output-tree.root --writeInputToTxt IN:in.txt --useAthenaPackages --outputs TREE:output-tree.root --noEmail --framework easyjet --notExpandInDS --athenaTag AthAnalysis,25.2.105 --inTarBall code.tar.gz
INFO : upload sandbox
INFO : submit user.alaha.testmc23e.2026_08_12_T173338.546597.e8588_a934_r16083_p6697/
INFO : succeeded. new jediTaskID=51980817
 
prun --inDS mc23_13p6TeV.546598.MGPy8EG_lv_offsh_mZp_1000_mumu.deriv.DAOD_PHYS.e8588_a934_r16083_p6697 --outDS user.alaha.testmc23e.2026_08_12_T173338.546598.e8588_a934_r16083_p6697 --exec easyjet-ntupler %IN -l --run-config config.yaml --out-file output-tree.root --writeInputToTxt IN:in.txt --useAthenaPackages --outputs TREE:output-tree.root --noEmail --framework easyjet --notExpandInDS --athenaTag AthAnalysis,25.2.105 --inTarBall code.tar.gz
INFO : upload sandbox
INFO : submit user.alaha.testmc23e.2026_08_12_T173338.546598.e8588_a934_r16083_p6697/
INFO : succeeded. new jediTaskID=51980820
```

**How to check status of the grid jobs**
```bash
pbook showl <jediTaskID>
```
#output
```
$ pbook showl 51980817

PBook user: Arnab Laha 
Showing only max 1000 tasks in last 14 days. One can set days=N to see tasks in last N days, and limit=M to see at most M latest tasks 
                                                                                                                                                                                                                                      
  JediTaskID   Status   CreationDate          ModificationTime      ReqID   Progress   Files (done|failed|total)   TaskName                                                                  URL                                      
 ──────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────── 
    51980817     done   2026-08-12 15:35:26   2026-08-12 16:16:13       2       100%   2|0|2                       user.alaha.testmc23e.2026_08_12_T173338.546597.e8588_a934_r16083_p6697/   https://bigpanda.cern.ch/task/51980817/  

```

