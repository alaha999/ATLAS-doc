### Background MC samples details

location:
- mc20e (2018): `/afs/cern.ch/work/a/alaha/public/ATLAS/HiggsDilepAnalysis/LLMETRun2_v1`

##### ttbar + singletop s-channel, t-channel + associated top

| Sample label | DSID | Dataset | Comments |
|---|---:|---|---|
| `Powheg_ttbar_dil` | `410472` | `mc20_13TeV.410472.PhPy8EG_A14_ttbar_hdamp258p75_dil.deriv.DAOD_PHYS` | ttbar with both W bosons decaying leptonically |
| `Powheg_ttbar_nonallhad` | `410470` | `mc20_13TeV.410470.PhPy8EG_A14_ttbar_hdamp258p75_nonallhad.deriv.DAOD_PHYS` | ttbar with at least one W decaying leptonically |
| `Powheg_st_schan_top` | `410644` | `mc20_13TeV.410644.PowhegPythia8EvtGen_A14_singletop_schan_lept_top.deriv.DAOD_PHYS` | s-channel single top with leptonic W decay |
| `Powheg_st_schan_atop` | `410645` | `mc20_13TeV.410645.PowhegPythia8EvtGen_A14_singletop_schan_lept_antitop.deriv.DAOD_PHYS` | s-channel single antitop with leptonic W decay |
| `Powheg_st_tchan_top` | `410658` | `mc20_13TeV.410658.PhPy8EG_A14_tchan_BW50_lept_top.deriv.DAOD_PHYS` | t-channel single top with leptonic W decay |
| `Powheg_st_tchan_atop` | `410659` | `mc20_13TeV.410659.PhPy8EG_A14_tchan_BW50_lept_antitop.deriv.DAOD_PHYS` | t-channel single antitop with leptonic W decay |
| `Powheg_Wt_dil_top` | `410648` | `mc20_13TeV.410648.PowhegPythia8EvtGen_A14_Wt_DR_dilepton_top.deriv.DAOD_PHYS` | Wt associated production, dileptonic |
| `Powheg_Wt_dil_atop` | `410649` | `mc20_13TeV.410649.PowhegPythia8EvtGen_A14_Wt_DR_dilepton_antitop.deriv.DAOD_PHYS` | W-antitop associated production, dileptonic |
| `Powheg_Wt_incl_top` | `410646` | `mc20_13TeV.410646.PowhegPythia8EvtGen_A14_Wt_DR_inclusive_top.deriv.DAOD_PHYS` | Wt associated production, inclusive decays |
| `Powheg_Wt_incl_atop` | `410647` | `mc20_13TeV.410647.PowhegPythia8EvtGen_A14_Wt_DR_inclusive_antitop.deriv.DAOD_PHYS` | W-antitop associated production, inclusive decays |

##### Top + EW Bosons (ttV, ttVV)

| Sample label | DSID | Dataset | Comments |
|---|---:|---|---|
| `aMC_ttW` | `410155` | `mc20_13TeV.410155.aMcAtNloPythia8EvtGen_MEN30NLO_A14N23LO_ttW.deriv.DAOD_PHYS` | ttbar produced with a W boson |
| `MG_ttWW` | `410081` | `mc20_13TeV.410081.MadGraphPythia8EvtGen_A14NNPDF23_ttbarWW.deriv.DAOD_PHYS` | ttbar produced with two W bosons |
| `aMC_ttZqq` | `410157` | `mc20_13TeV.410157.aMcAtNloPythia8EvtGen_MEN30NLO_A14N23LO_ttZqq.deriv.DAOD_PHYS` | ttbar + Z, Z to quarks |
| `aMC_ttZnunu` | `410156` | `mc20_13TeV.410156.aMcAtNloPythia8EvtGen_MEN30NLO_A14N23LO_ttZnunu.deriv.DAOD_PHYS` | ttbar + Z, Z to neutrinos |
| `aMC_ttee` | `410218` | `mc20_13TeV.410218.aMcAtNloPythia8EvtGen_MEN30NLO_A14N23LO_ttee.deriv.DAOD_PHYS` | ttbar plus an electron pair |
| `aMC_ttmumu` | `410219` | `mc20_13TeV.410219.aMcAtNloPythia8EvtGen_MEN30NLO_A14N23LO_ttmumu.deriv.DAOD_PHYS` | ttbar plus a muon pair |

##### Sherpa Z + Jets (Drell-Yan)

| Sample label | DSID | Dataset | Comments |
|---|---:|---|---|
| `Sherpa_Zee_B` | `700320` | `mc20_13TeV.700320.Sh_2211_Zee_maxHTpTV2_BFilter.deriv.DAOD_PHYS` | Z to ee + jets; b-hadron filter |
| `Sherpa_Zee_C` | `700321` | `mc20_13TeV.700321.Sh_2211_Zee_maxHTpTV2_CFilterBVeto.deriv.DAOD_PHYS` | Z to ee + jets; c-filter, b-veto |
| `Sherpa_Zee_L` | `700322` | `mc20_13TeV.700322.Sh_2211_Zee_maxHTpTV2_CVetoBVeto.deriv.DAOD_PHYS` | Z to ee + jets; b- and c-veto |
| `Sherpa_Zmumu_B` | `700323` | `mc20_13TeV.700323.Sh_2211_Zmumu_maxHTpTV2_BFilter.deriv.DAOD_PHYS` | Z to mumu + jets; b-hadron filter |
| `Sherpa_Zmumu_C` | `700324` | `mc20_13TeV.700324.Sh_2211_Zmumu_maxHTpTV2_CFilterBVeto.deriv.DAOD_PHYS` | Z to mumu + jets; c-filter, b-veto |
| `Sherpa_Zmumu_L` | `700325` | `mc20_13TeV.700325.Sh_2211_Zmumu_maxHTpTV2_CVetoBVeto.deriv.DAOD_PHYS` | Z to mumu + jets; b- and c-veto |
| `Sherpa_Ztautau_LL_B` | `700326` | `mc20_13TeV.700326.Sh_2211_Ztautau_LL_maxHTpTV2_BFilter.deriv.DAOD_PHYS` | Z to tautau (both leptonic) + jets; b-filter |
| `Sherpa_Ztautau_LL_C` | `700327` | `mc20_13TeV.700327.Sh_2211_Ztautau_LL_maxHTpTV2_CFilterBVeto.deriv.DAOD_PHYS` | Z to tautau (both leptonic) + jets; c-filter, b-veto |
| `Sherpa_Ztautau_LL_L` | `700328` | `mc20_13TeV.700328.Sh_2211_Ztautau_LL_maxHTpTV2_CVetoBVeto.deriv.DAOD_PHYS` | Z to tautau (both leptonic) + jets; b/c-veto |
| `Sherpa_Ztautau_LH_B` | `700329` | `mc20_13TeV.700329.Sh_2211_Ztautau_LH_maxHTpTV2_BFilter.deriv.DAOD_PHYS` | Z to tautau (leptonic/hadronic) + jets; b-filter |
| `Sherpa_Ztautau_LH_C` | `700330` | `mc20_13TeV.700330.Sh_2211_Ztautau_LH_maxHTpTV2_CFilterBVeto.deriv.DAOD_PHYS` | Z to tautau (leptonic/hadronic) + jets; c-filter, b-veto |
| `Sherpa_Ztautau_LH_L` | `700331` | `mc20_13TeV.700331.Sh_2211_Ztautau_LH_maxHTpTV2_CVetoBVeto.deriv.DAOD_PHYS` | Z to tautau (leptonic/hadronic) + jets; b/c-veto |
| `Sherpa_Ztautau_HH_B` | `700332` | `mc20_13TeV.700332.Sh_2211_Ztautau_HH_maxHTpTV2_BFilter.deriv.DAOD_PHYS` | Z to tautau (both hadronic) + jets; b-filter |
| `Sherpa_Ztautau_HH_C` | `700333` | `mc20_13TeV.700333.Sh_2211_Ztautau_HH_maxHTpTV2_CFilterBVeto.deriv.DAOD_PHYS` | Z to tautau (both hadronic) + jets; c-filter, b-veto |
| `Sherpa_Ztautau_HH_L` | `700334` | `mc20_13TeV.700334.Sh_2211_Ztautau_HH_maxHTpTV2_CVetoBVeto.deriv.DAOD_PHYS` | Z to tautau (both hadronic) + jets; b/c-veto |

##### Z + 2 jets (electroweak production)

| Sample label | DSID | Dataset | Comments |
|---|---:|---|---|
| `Sherpa_EW_Zeejj` | `700358` | `mc20_13TeV.700358.Sh_2211_Zee2jets_Min_N_TChannel.deriv.DAOD_PHYS` | Electroweak Z to ee + two jets |
| `Sherpa_EW_Zmumujj` | `700359` | `mc20_13TeV.700359.Sh_2211_Zmm2jets_Min_N_TChannel.deriv.DAOD_PHYS` | Electroweak Z to mumu + two jets |
| `Sherpa_EW_Ztautaujj` | `700360` | `mc20_13TeV.700360.Sh_2211_Ztt2jets_Min_N_TChannel.deriv.DAOD_PHYS` | Electroweak Z to tautau + two jets |

##### Powheg ZZ
| Sample label | DSID | Dataset | Comments |
|---|---:|---|---|
| `Powheg_ZZ4L` | `361603` | `mc20_13TeV.361603.PowhegPy8EG_CT10nloME_AZNLOCTEQ6L1_ZZllll_mll4.deriv.DAOD_PHYS` | ZZ to four charged leptons |
| `Powheg_ZZllvv` | `361604` | `mc20_13TeV.361604.PowhegPy8EG_CT10nloME_AZNLOCTEQ6L1_ZZvvll_mll4.deriv.DAOD_PHYS` | ZZ to two charged leptons and two neutrinos |

##### Sherpa Four-Fermion / Diboson

| Sample label | DSID | Dataset | Comments |
|---|---:|---|---|
| `Sherpa_llll` | `700600` | `mc20_13TeV.700600.Sh_2212_llll.deriv.DAOD_PHYS` | Four charged leptons; neutral-current contributions including ZZ, Zγ* and γ*γ* |
| `Sherpa_lllljj` | `700587` | `mc20_13TeV.700587.Sh_2212_lllljj.deriv.DAOD_PHYS` | Four charged leptons + two partons |
| `Sherpa_llvv_OS` | `700602` | `mc20_13TeV.700602.Sh_2212_llvv_os.deriv.DAOD_PHYS` | Opposite-sign dileptons + two neutrinos; WW/ZZ contributions |
| `Sherpa_llvvjj_OS` | `700589` | `mc20_13TeV.700589.Sh_2212_llvvjj_os.deriv.DAOD_PHYS` | Opposite-sign dileptons + two neutrinos + two partons |
| `Sherpa_ZZllqq` | `700493` | `mc20_13TeV.700493.Sh_2211_ZqqZll.deriv.DAOD_PHYS` | ZZ production with Z→qq and Z→ll |
| `Sherpa_ggZZllvv` | `345723` | `mc20_13TeV.345723.Sherpa_222_NNPDF30NNLO_ggllvvZZ.deriv.DAOD_PHYS` | Gluon-induced ZZ→llνν |

##### Powheg WWlvlv

| Sample label | DSID | Dataset | Comments |
|---|---:|---|---|
| `Powheg_WWlvlv` | `361600` | `mc20_13TeV.361600.PowhegPy8EG_CT10nloME_AZNLOCTEQ6L1_WWlvlv.deriv.DAOD_PHYS` | WW to two charged leptons and two neutrinos |

###### Sherpa WWlvlv gluon induced

| Sample label | DSID | Dataset | Comments |
|---|---:|---|---|
| `Sherpa_ggWWlvlv` | `345718` | `mc20_13TeV.345718.Sherpa_222_NNPDF30NNLO_ggllvvWW.deriv.DAOD_PHYS` | Gluon-induced WW to leptons and neutrinos |

##### Powheg WZ

| Sample label | DSID | Dataset | Comments |
|---|---:|---|---|
| `Powheg_WZlvll` | `361601` | `mc20_13TeV.361601.PowhegPy8EG_CT10nloME_AZNLOCTEQ6L1_WZlvll_mll4.deriv.DAOD_PHYS` | W to lepton+neutrino; Z to two leptons |
| `Powheg_WZqqll` | `361607` | `mc20_13TeV.361607.PowhegPy8EG_CT10nloME_AZNLOCTEQ6L1_WZqqll_mll20.deriv.DAOD_PHYS` | W to quarks; Z to two leptons |

##### Sherpa VV — Three Leptons + Neutrino

| Sample label | DSID | Dataset | Comments |
|---|---:|---|---|
| `Sherpa_VVlllv` | `700601` | `mc20_13TeV.700601.Sh_2212_lllv.deriv.DAOD_PHYS` | Three charged leptons + neutrino; predominantly WZ, potentially including Wγ* contributions |
| `Sherpa_VVlllvjj` | `700588` | `mc20_13TeV.700588.Sh_2212_lllvjj.deriv.DAOD_PHYS` | Three charged leptons + neutrino + two partons; predominantly WZ, potentially including Wγ* contributions |


##### Higgs: H → Zγ

| Sample label | DSID | Dataset | Comments |
|---|---:|---|---|
| `Powheg_ggH_Zgamma` | `345316` | `mc20_13TeV.345316.PowhegPythia8EvtGen_NNLOPS_nnlo_30_ggH125_Zy_Zll.deriv.DAOD_PHYS` | Gluon-fusion H to Zgamma, Z to leptons |
| `Powheg_VBFH_Zgamma` | `345833` | `mc20_13TeV.345833.PowhegPythia8EvtGen_NNPDF30_AZNLOCTEQ6L1_VBFH125_Zllgam.deriv.DAOD_PHYS` | VBF H to Zgamma, Z to leptons |
| `Powheg_WmH_Zgamma` | `345320` | `mc20_13TeV.345320.PowhegPythia8EvtGen_NNPDF30_AZNLO_WmH125J_HZy_Wincl_MINLO.deriv.DAOD_PHYS` | W- H associated production, H to Zgamma |
| `Powheg_WpH_Zgamma` | `345321` | `mc20_13TeV.345321.PowhegPythia8EvtGen_NNPDF30_AZNLO_WpH125J_HZy_Wincl_MINLO.deriv.DAOD_PHYS` | W+ H associated production, H to Zgamma |
| `Powheg_ZH_Zgamma` | `345322` | `mc20_13TeV.345322.PowhegPythia8EvtGen_NNPDF30_AZNLO_ZH125J_HZy_Zincl_MINLO.deriv.DAOD_PHYS` | ZH associated production, H to Zgamma |

##### Higgs: H → WW

| Sample label | DSID | Dataset | Comments |
|---|---:|---|---|
| `Powheg_ggH_WW` | `345324` | `mc20_13TeV.345324.PowhegPythia8EvtGen_NNLOPS_NN30_ggH125_WWlvlv_EF_15_5.deriv.DAOD_PHYS` | Gluon-fusion H to WW* to leptons and neutrinos |
| `Powheg_VBFH_WW` | `345948` | `mc20_13TeV.345948.PowhegPy8EG_NNPDF30_AZNLOCTEQ6L1_VBFH125_WWlvlv.deriv.DAOD_PHYS` | VBF H to WW* to leptons and neutrinos |

##### Higgs: Invisible Decays

| Sample label | DSID | Dataset | Comments |
|---|---:|---|---|
| `Powheg_ggZH_HZZinv` | `345596` | `mc20_13TeV.345596.PowhegPythia8EvtGen_NNPDF3_AZNLO_ggZH125_Zinc_HZZinv.deriv.DAOD_PHYS` | Gluon-induced ZH, H to ZZ invisible configuration |

##### Sherpa Dilepton + Photon (Z/γ* + γ)

| Sample label | DSID | Dataset | Comments |
|---|---:|---|---|
| `Sherpa_llgamma_mumu` | `700398` | `mc20_13TeV.700398.Sh_2211_mumugamma.deriv.DAOD_PHYS` | μμγ final state; Zγ and γ*γ contributions |
| `Sherpa_llgamma_ee` | `700399` | `mc20_13TeV.700399.Sh_2211_eegamma.deriv.DAOD_PHYS` | eeγ final state; Zγ and γ*γ contributions |
| `Sherpa_llgamma_tautau` | `700400` | `mc20_13TeV.700400.Sh_2211_tautaugamma.deriv.DAOD_PHYS` | ττγ final state; Zγ and γ*γ contributions |

##### Higgs: H → ZZ → 4l
| Sample label | DSID | Dataset | Comments |
|---|---:|---|---|
| `Powheg_ggH_ZZ4L` | `346701` | `mc20_13TeV.346701.PhPy8EG_Hto4l_NNLOPS_nnlo_30_ggH125_ZZ4l.deriv.DAOD_PHYS` | Gluon-fusion H to ZZ* to four charged leptons |
| `Powheg_VBFH_incl` | `346317` | `mc20_13TeV.346317.PowhegPy8EG_NNPDF30_AZNLOCTEQ6L1_VBFH125_incl.deriv.DAOD_PHYS` | Inclusive VBF Higgs; no decay restricted in name |
| `Powheg_ggZH_ZZ4L` | `346697` | `mc20_13TeV.346697.PhPy8EG_Prophecy_NNPDF3_AZNLO_ggZH125_ZZ4lepZinc.deriv.DAOD_PHYS` | Gluon-induced ZH, H to ZZ* to four charged leptons |

##### Triboson (VVV) Sherpa

| Sample label | DSID | Dataset | Comments |
|---|---:|---|---|
| `Sherpa_WWW_3l3v` | `364242` | `mc20_13TeV.364242.Sherpa_222_NNPDF30NNLO_WWW_3l3v_EW6.deriv.DAOD_PHYS` | WWW with three leptons and three neutrinos |
| `Sherpa_WWZ_4l2v` | `364243` | `mc20_13TeV.364243.Sherpa_222_NNPDF30NNLO_WWZ_4l2v_EW6.deriv.DAOD_PHYS` | WWZ with four leptons and two neutrinos |
| `Sherpa_WWZ_2l4v` | `364244` | `mc20_13TeV.364244.Sherpa_222_NNPDF30NNLO_WWZ_2l4v_EW6.deriv.DAOD_PHYS` | WWZ with two leptons and four neutrinos |
| `Sherpa_WZZ_5l1v` | `364245` | `mc20_13TeV.364245.Sherpa_222_NNPDF30NNLO_WZZ_5l1v_EW6.deriv.DAOD_PHYS` | WZZ with five leptons and one neutrino |
| `Sherpa_WZZ_3l3v` | `364246` | `mc20_13TeV.364246.Sherpa_222_NNPDF30NNLO_WZZ_3l3v_EW6.deriv.DAOD_PHYS` | WZZ with three leptons and three neutrinos |
| `Sherpa_ZZZ_6l0v` | `364247` | `mc20_13TeV.364247.Sherpa_222_NNPDF30NNLO_ZZZ_6l0v_EW6.deriv.DAOD_PHYS` | ZZZ with six charged leptons |
| `Sherpa_ZZZ_4l2v` | `364248` | `mc20_13TeV.364248.Sherpa_222_NNPDF30NNLO_ZZZ_4l2v_EW6.deriv.DAOD_PHYS` | ZZZ with four leptons and two neutrinos |
| `Sherpa_ZZZ_2l4v` | `364249` | `mc20_13TeV.364249.Sherpa_222_NNPDF30NNLO_ZZZ_2l4v_EW6.deriv.DAOD_PHYS` | ZZZ with two leptons and four neutrinos |
