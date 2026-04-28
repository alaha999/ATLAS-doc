Available configs
-------------------
- `ej_config_cutbased_tagger.py`: Tagger definition, LargeR and EJ trigger region, mistag map calculation (More runtime due to 2D histograms, more calculation, larger size hist file)
- `ej_config_cutbased_evaluation.py`: 1D variable plots after mistag map application, Observed and Prediction plots, closure studies (Fast, just evaluation)
- `ej_config_minianalysis.yaml`: CutFlow analysis and N-1 style cutflow plots for Large-R and EJ trigger region (Moderate, minianalysis for quick study, cut threshold, etc)

Example fastframe commands. Limited signal points are used to develop the method.

EJ Trigger Region
------------------
Low mass Zprime + tchannel:

```python
python3 FastFrames.py --step h --config ../../configs/ej_config_cutbased_tagger.yaml --sample Sig_pi10_Zp600_l5,Sig_pi10_Zp600_l50,Sig_pi10_Zp600_l100,Sig_pi5_Xd600_l5,Sig_pi5_Xd600_l50,Sig_pi5_Xd600_l500
```

Large-R Trigger Region
-----------------------
High mass Zprime + tchannel:

```python
python3 FastFrames.py --step h --config ../../configs/ej_config_cutbased_tagger.yaml --sample Sig_pi10_Zp1500_l5,Sig_pi10_Zp1500_l50,Sig_pi10_Zp1500_l100,Sig_pi10_Zp3000_l5,Sig_pi10_Zp3000_l50,Sig_pi5_Zp3000_l5,Sig_pi5_Zp3000_l50,Sig_pi5_Zp3000_l50,Sig_pi20_Zp3000_l5,Sig_pi20_Zp3000_l50,Sig_pi10_Xd1500_l5,Sig_pi10_Xd1500_l50,Sig_pi20_Xd1500_l5,Sig_pi20_Xd1500_l50,Sig_pi5_Xd1500_l5,Sig_pi5_Xd1500_l50
```
High mass t-channel:

```python
python3 FastFrames.py --step h --config ../../configs/ej_config_cutbased_tagger.yaml --sample Sig_pi10_Xd1500_l5,Sig_pi10_Xd1500_l50,Sig_pi20_Xd1500_l5,Sig_pi20_Xd1500_l50,Sig_pi5_Xd1500_l5,Sig_pi5_Xd1500_l50`
```
High mass Zprime:

```python
python3 FastFrames.py --step h --config ../../configs/ej_config_cutbased_tagger.yaml --sample Sig_pi10_Zp1500_l5,Sig_pi10_Zp1500_l50,Sig_pi10_Zp1500_l100,Sig_pi10_Zp3000_l5,Sig_pi10_Zp3000_l50,Sig_pi5_Zp3000_l5,Sig_pi5_Zp3000_l50,Sig_pi5_Zp3000_l50,Sig_pi20_Zp3000_l5,Sig_pi20_Zp3000_l50

```

### Batch Submit at lxplus
```python
python3 batch_submit.py -c ../../configs/ej_config_cutbased_tagger.yaml --step h --custom-class-path ../../EJFrame/ --split-n-jobs 100 --samples qcdbkg --timestamp
```

### Merge-files after batch jobs
```python
python3 fastframes/python/merge_jobs.py --config configs/ej_config_cutbased_tagger.yaml --samples qcdbkg
```
