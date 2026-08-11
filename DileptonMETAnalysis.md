# Dilepton + MET analysis

Do we have Run-3 HZyd DAOD_PHYS samples?
- No run-3 samples
- We have a few mc20 samples.

```bash
ami list datasets "mc20_13TeV.603891.%.deriv.DAOD_PHYS.%"
mc20_13TeV.603891.PhPy8EG_ggH_HZyd_Zll.deriv.DAOD_PHYS.e8575_e8455_s3797_r13145_r13146_p6266
mc20_13TeV.603891.PhPy8EG_ggH_HZyd_Zll.deriv.DAOD_PHYS.e8575_e8455_s3797_r13167_r13146_p6266
mc20_13TeV.603891.PhPy8EG_ggH_HZyd_Zll.deriv.DAOD_PHYS.e8575_s3797_r13145_p6266
mc20_13TeV.603891.PhPy8EG_ggH_HZyd_Zll.deriv.DAOD_PHYS.e8575_s3797_r13167_p6266
```
```bash
ami list datasets "mc20_13TeV.603892.%.deriv.DAOD_PHYS.%"
mc20_13TeV.603892.PhPy8EG_vbf_HZyd_Zll.deriv.DAOD_PHYS.e8575_e8455_s3797_r13144_r13146_p6266
mc20_13TeV.603892.PhPy8EG_vbf_HZyd_Zll.deriv.DAOD_PHYS.e8575_e8455_s3797_r13145_r13146_p6266
mc20_13TeV.603892.PhPy8EG_vbf_HZyd_Zll.deriv.DAOD_PHYS.e8575_s3797_r13144_p6266
mc20_13TeV.603892.PhPy8EG_vbf_HZyd_Zll.deriv.DAOD_PHYS.e8575_s3797_r13145_p6266


```

### Tag and Campaign map
Useful links:
- `Top CP page:` https://topcptoolkit.docs.cern.ch/latest/tutorials/submit_grid/?utm_source=chatgpt.com#reconstruction
- `ATLAS MC Production Twiki:` https://twiki.cern.ch/twiki/bin/viewauth/AtlasProtected/AtlasProductionGroup?extralog=-%20caching%20topic#Specific_Information_on_MC_campa
- `DerivationProductionTwiki:` https://twiki.cern.ch/twiki/bin/view/AtlasProtected/DerivationProductionTeam

- `r13167`: 2015-1016 (mc20a)
- `r13144`: 2017 (mc20d)
- `r13145`: 2018 (mc20e)
- `p6266`: Derivation Tag

### DSID and Samples
| DSID | Physics Short | Xsec [pb] | genFilEff | k-factor | Eff. Xsec [pb] |
|---:|---|---:|---:|---:|---:|
| 603891 | PhPy8EG_ggH_HZyd_Zll | 28.306 | 0.52461 | 1 | 14.8496 |
| 603892 | PhPy8EG_vbf_HZyd_Zll | 3.7485 | 0.545412 | 1 | 2.04448 |
| 410472 | PhPy8EG_A14_ttbar_hdamp258p75_dil | 729.77 | 0.105 | 1.14269 | 87.5595 |
| 700602 | Sh_2212_llvv_os | 12.079 | 1 | 1 | 12.079 |
| 700320 | Sh_2211_Zee_maxHTpTV2_BFilter | 2221.2 | 0.0249359 | 1 | 55.3877 |
| 700321 | Sh_2211_Zee_maxHTpTV2_CFilterBVeto | 2221.2 | 0.129814 | 1 | 288.344 |
| 700323 | Sh_2211_Zmumu_maxHTpTV2_BFilter | 2221.3 | 0.0243944 | 1 | 54.1873 |
| 700324 | Sh_2211_Zmumu_maxHTpTV2_CFilterBVeto | 2221.3 | 0.13003 | 1 | 288.836 |
| 700792 | Sh_2214_Ztautau_maxHTpTV2_BFilter | 2239.6 | 0.0248653 | 1 | 55.6882 |


