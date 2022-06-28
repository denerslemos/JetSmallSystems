# Jet pPb analysis at 8.16 TeV

This branch contain relevant information about the data processing of pPb at 8.16 TeV dataset collected by CMS in the Run2 at November/December of 2016. In addition, the status and step-by-step usage of the codes are included as follows:

## Code structure and steps:

HiForest production -> Make the skims -> produce histograms -> run macros for plots

> HiForest
> > Setup for official HiForest setup. Intructions to add event plane informations are also included

> List_of_files
> > To make it easy and fast the skim production I already include the list of forest files for data and MC in this folder (list_of_forest_p-going_X.txt or list_of_forest_Pb-going_X.txt):
> > > Where X can be MB for minimum bias, HM for high multiplicity and JETS for jet samples
> > > >
> > > Or EPOS, AMPT and HIJING for respective MC MB samples 
> > > > 
> > > Or PYTHIA8_Y, where Y means pthat greater than Y for embedded and unembedded samples

> Skim
> > Produce the skims using HiForest as input. We can use CRAB3 or HTCondor to production and is useful to reduce the size of files.

> Histo
> > C++ code using ROOT framework to produce the histograms for analysis: Delta R, 2PC, ... . Mixing is done at this step.

> Macros
> > Codes using ROOT to produce the result plots, fits and so on for our analysis 

## Status:

1. HiForest production: Ongoing -> stored at T2_BR_SPRACE (just remember to use /store/user/...)
   - Data
     - [ ] MB - Ntrkoff -> range [0,185] -> It has more statistics than HM0 in the range [120, 185] :)
       - p-going: 
         - [x] /ddesouza/PAMinimumBias1/HeavyIon_Forest_pPb_8p16TeV_pgoing_Trigger_MB_PD1/220413_170920/*
         - [x] /ddesouza/PAMinimumBias2/HeavyIon_Forest_pPb_8p16TeV_pgoing_Trigger_MB_PD2/220413_171031/*
         - [x] /caber/PAMinimumBias3/HeavyIon_Forest_pPb_8p16TeV_pgoing_Trigger_MB_PD3/220413_201132/*
         - [x] /caber/PAMinimumBias4/HeavyIon_Forest_pPb_8p16TeV_pgoing_Trigger_MB_PD4/220413_201343/*
         - [x] /ddesouza/PAMinimumBias5/HeavyIon_Forest_pPb_8p16TeV_pgoing_Trigger_MB_PD5/220420_162052/*
         - [x] /ddesouza/PAMinimumBias6/HeavyIon_Forest_pPb_8p16TeV_pgoing_Trigger_MB_PD6/220420_162808/*
         - [x] /ahingraj/PAMinimumBias7/HeavyIon_Forest_pPb_8p16TeV_pgoing_Trigger_MB_PD7/220425_173932/*
         - [x] /ahingraj/PAMinimumBias8/HeavyIon_Forest_pPb_8p16TeV_pgoing_Trigger_MB_PD8/220425_174127/*
       - Pb-going:
         - [x] /caber/PAMinimumBias1/HeavyIon_Forest_pPb_8p16TeV_Pbgoing_Trigger_MB_PD1/220524_193354/*
         - [x] /caber/PAMinimumBias2/HeavyIon_Forest_pPb_8p16TeV_Pbgoing_Trigger_MB_PD2/220524_193533/*
         - [x] /sdogra/PAMinimumBias3/HeavyIon_Forest_pPb_8p16TeV_Pbgoing_Trigger_MB_PD3/220525_022016/*
         - [ ] --> Sunil
         - [ ] X
         - [ ] X
         - [ ] X
         - [ ] X
         - [ ] --> Abhishek
         - [ ] X
         - [ ] /caber/PAMinimumBias12/HeavyIon_Forest_pPb_8p16TeV_Pbgoing_Trigger_MB_PD12/220626_192407/*
         - [ ] /ddesouza/PAMinimumBias13/HeavyIon_Forest_pPb_8p16TeV_Pbgoing_Trigger_MB_PD13/220626_183646/*
         - [ ] X
         - [x] /ddesouza/PAMinimumBias15/HeavyIon_Forest_pPb_8p16TeV_Pbgoing_Trigger_MB_PD15/220524_161505/*
         - [x] /ddesouza/PAMinimumBias16/HeavyIon_Forest_pPb_8p16TeV_Pbgoing_Trigger_MB_PD16/220524_161140/*
         - [x] /ahingraj/PAMinimumBias17/HeavyIon_Forest_pPb_8p16TeV_Pbgoing_Trigger_MB_PD17/220524_161145/*
         - [x] /ahingraj/PAMinimumBias18/HeavyIon_Forest_pPb_8p16TeV_Pbgoing_Trigger_MB_PD18/220524_161301/*
         - [x] /borzari/PAMinimumBias19/HeavyIon_Forest_pPb_8p16TeV_Pbgoing_Trigger_MB_PD19/220426_135622/*
         - [x] /borzari/PAMinimumBias20/HeavyIon_Forest_pPb_8p16TeV_Pbgoing_Trigger_MB_PD20/220426_135719/*
     - [x] HM - Ntrkoff -> range [185, 250] (PD's 1 to 6)
       - p-going: 
         - [x] /ddesouza/PAHighMultiplicity1/HeavyIon_Forest_pPb_8p16TeV_pgoing_Trigger_HM185_PD1/220326_030954/*
         - [x] /ddesouza/PAHighMultiplicity2/HeavyIon_Forest_pPb_8p16TeV_pgoing_Trigger_HM185_PD2/220326_031425/*
         - [x] /borzari/PAHighMultiplicity3/HeavyIon_Forest_pPb_8p16TeV_pgoing_Trigger_HM185_PD3/220326_152218/*
         - [x] /borzari/PAHighMultiplicity4/HeavyIon_Forest_pPb_8p16TeV_pgoing_Trigger_HM185_PD4/220326_152246/*
         - [x] /caber/PAHighMultiplicity5/HeavyIon_Forest_pPb_8p16TeV_pgoing_Trigger_HM185_PD5/220326_182617/*
         - [x] /caber/PAHighMultiplicity6/HeavyIon_Forest_pPb_8p16TeV_pgoing_Trigger_HM185_PD6/220326_182730/*
       - Pb-going:
         - [x] /ahingraj/PAHighMultiplicity1/HeavyIon_Forest_pPb_8p16TeV_Pbgoing_Trigger_HM185_PD1/220327_002010/*
         - [x] /ahingraj/PAHighMultiplicity2/HeavyIon_Forest_pPb_8p16TeV_Pbgoing_Trigger_HM185_PD2/220327_002150/*
         - [x] /ddesouza/PAHighMultiplicity3/HeavyIon_Forest_pPb_8p16TeV_Pbgoing_Trigger_HM185_PD3/220508_173510/*
         - [x] /ddesouza/PAHighMultiplicity4/HeavyIon_Forest_pPb_8p16TeV_Pbgoing_Trigger_HM185_PD4/220508_173553/* 
         - [x] /ddesouza/PAHighMultiplicity5/HeavyIon_Forest_pPb_8p16TeV_Pbgoing_Trigger_HM185_PD5/220401_154028/*
         - [x] /ddesouza/PAHighMultiplicity6/HeavyIon_Forest_pPb_8p16TeV_Pbgoing_Trigger_HM185_PD6/220401_154217/*
     - [x] HM - Ntrkoff -> range [250, inf] (PD 7)
       - p-going: /ddesouza/PAHighMultiplicity7/HeavyIon_Forest_pPb_8p16TeV_pgoing_Trigger_HM250/220327_024216/*
       - Pb-going: /ddesouza/PAHighMultiplicity7/HeavyIon_Forest_pPb_8p16TeV_Pbgoing_Trigger_HM250/220327_024248/*
     - [x] Jet samples -> EP information not included
       - p-going: /ddesouza/PAEGJet1/HiForest_pPb_8TeV_p-going_JetSamples_out/211211_161432/*
       - Pb-going: /ddesouza/PAEGJet1/HiForest_pPb_8TeV_Pb-going_JetSamples_out/211211_162021/*

   - MC simulations: Ongoing -> stored at T2_BR_SPRACE -> checking why jets are not available
     - [ ] EPOS MB
         - p-going: 
         - Pb-going:
         
     - [ ] HIJING MB
         - p-going: 
         - Pb-going:
         
     - [ ] AMPT MB
         - p-going: 
         - Pb-going:
         
     - [x] Pythia8 - Dijet - unembedded - EP information not included
       - [x] pthat > 15 GeV 
         - p-going:  /ddesouza/Dijet_pThat-15_pPb-Bst_8p16_Pythia8/New_HiForest_pPb_PYTHIA8_pthat15_p-going_out/220105_185751/0000
         - Pb-going: /ddesouza/Dijet_pThat-15_PbP-Bst_8p16_Pythia8/New_HiForest_pPb_PYTHIA8_pthat15_Pb-going_out/220105_190525/0000
       - [x] pthat > 30 GeV 
         - p-going:  /ddesouza/Dijet_pThat-30_pPb-Bst_8p16_Pythia8/New_HiForest_pPb_PYTHIA8_pthat30_p-going_out/220105_190608/0000
         - Pb-going: /ddesouza/Dijet_pThat-30_PbP-Bst_8p16_Pythia8/New_HiForest_pPb_PYTHIA8_pthat30_Pb-going_out/220105_190651/0000
       - [x] pthat > 50 GeV 
         - p-going:  /ddesouza/Dijet_pThat-50_pPb-Bst_8p16_Pythia8/New_HiForest_pPb_PYTHIA8_pthat50_p-going_out/220105_190734/0000
         - Pb-going: /ddesouza/Dijet_pThat-50_PbP-Bst_8p16_Pythia8/New_HiForest_pPb_PYTHIA8_pthat50_Pb-going_out/220105_190818/0000
       - [x] pthat > 80 GeV
         - p-going:  /ddesouza/Dijet_pThat-80_pPb-Bst_8p16_Pythia8/New_HiForest_pPb_PYTHIA8_pthat80_p-going_out/220105_190900/0000
         - Pb-going: /ddesouza/Dijet_pThat-80_PbP-Bst_8p16_Pythia8/New_HiForest_pPb_PYTHIA8_pthat80_Pb-going_out/220105_190943/0000
       - [x] pthat > 120 GeV 
         - p-going:  /ddesouza/Dijet_pThat-120_pPb-Bst_8p16_Pythia8/New_HiForest_pPb_PYTHIA8_pthat120_p-going_out/220105_191026/0000
         - Pb-going: /ddesouza/Dijet_pThat-120_PbP-Bst_8p16_Pythia8/New_HiForest_pPb_PYTHIA8_pthat120_Pb-going_out/220105_191109/0000
       - [x] pthat > 170 GeV      
         - p-going:  /ddesouza/Dijet_pThat-170_pPb-Bst_8p16_Pythia8/New_HiForest_pPb_PYTHIA8_pthat170_p-going_out/220120_044002/0000
         - Pb-going: /ddesouza/Dijet_pThat-170_PbP-Bst_8p16_Pythia8/New_HiForest_pPb_PYTHIA8_pthat170_Pb-going_out/220120_044448/0000
       - [x] pthat > 220 GeV
         - p-going:  /ddesouza/Dijet_pThat-220_pPb-Bst_8p16_Pythia8/New_HiForest_pPb_PYTHIA8_pthat220_p-going_out/220105_191152/0000
         - Pb-going: /ddesouza/Dijet_pThat-220_PbP-Bst_8p16_Pythia8/New_HiForest_pPb_PYTHIA8_pthat220_Pb-going_out/220105_191234/0000     
       - [x] pthat > 280 GeV
         - p-going:  /ddesouza/Dijet_pThat-280_pPb-Bst_8p16_Pythia8/New_HiForet_pPb_PYTHIA8_pthat280_p-going_out/220120_044020/0000
         - Pb-going: /ddesouza/Dijet_pThat-280_PbP-Bst_8p16_Pythia8/New_HiForest_pPb_PYTHIA8_pthat280_Pb-going_out/220120_044029/0000
       - [x] pthat > 370 GeV
         - p-going:  /ddesouza/Dijet_pThat-370_pPb-Bst_8p16_Pythia8/New_HiForest_pPb_PYTHIA8_pthat370_p-going_out/220105_191317/0000
         - Pb-going: /ddesouza/Dijet_pThat-370_PbP-Bst_8p16_Pythia8/New_HiForest_pPb_PYTHIA8_pthat370_Pb-going_out/220105_191400/0000
       - [x] pthat > 460 GeV
         - p-going:  /ddesouza/Dijet_pThat-460_pPb-Bst_8p16_Pythia8/New_HiForest_pPb_PYTHIA8_pthat460_p-going_out/220120_044039/0000
         - Pb-going: /ddesouza/Dijet_pThat-460_PbP-Bst_8p16_Pythia8/New_HiForest_pPb_PYTHIA8_pthat460_Pb-going_out/220120_044048/0000
       - [x] pthat > 540 GeV
         - p-going:  /ddesouza/Dijet_pThat-540_pPb-Bst_8p16_Pythia8/New_HiForest_pPb_PYTHIA8_pthat540_p-going_out/220105_191443/0000
         - Pb-going: /ddesouza/Dijet_pThat-540_PbP-Bst_8p16_Pythia8/New_HiForest_pPb_PYTHIA8_pthat540_Pb-going_out/220105_191528/0000
      
     - [x] Pythia8  - Dijet - embedded (using EPOS) - EP information not included
       - [x] pthat > 15 GeV
         - p-going:  /ddesouza/Dijet_pThat-15_pPb-EmbEPOS_8p16_Pythia8/New_HiForest_pPb_PYTHIA8_EPOS_emb_pthat15_p-going_out/220106_053602/0000  
         - Pb-going: /ddesouza/Dijet_pThat-15_PbP-EmbEPOS_8p16_Pythia8/New_HiForest_pPb_PYTHIA8_EPOS_emb_pthat15_Pb-going_out/220106_053611/0000
       - [x] pthat > 30 GeV 
         - p-going: /ddesouza/Dijet_pThat-30_pPb-EmbEPOS_8p16_Pythia8/New_HiForest_pPb_PYTHIA8_EPOS_emb_pthat30_p-going_out/220106_053620/0000
         - Pb-going: /ddesouza/Dijet_pThat-30_PbP-EmbEPOS_8p16_Pythia8/New_HiForest_pPb_PYTHIA8_EPOS_emb_pthat30_Pb-going_out/220106_053628/0000
       - [x] pthat > 50 GeV
         - p-going:  /ddesouza/Dijet_pThat-50_pPb-EmbEPOS_8p16_Pythia8/New_HiForest_pPb_PYTHIA8_EPOS_emb_pthat50_p-going_out/220106_053637/0000
         - Pb-going: /ddesouza/Dijet_pThat-50_PbP-EmbEPOS_8p16_Pythia8/New_HiForest_pPb_PYTHIA8_EPOS_emb_pthat50_Pb-going_out/220106_053646/0000
       - [x] pthat > 80 GeV
         - p-going:  /ddesouza/Dijet_pThat-80_pPb-EmbEPOS_8p16_Pythia8/New_HiForest_pPb_PYTHIA8_EPOS_emb_pthat80_p-going_out/220106_053655/0000
         - Pb-going: /ddesouza/Dijet_pThat-80_PbP-EmbEPOS_8p16_Pythia8/New_HiForest_pPb_PYTHIA8_EPOS_emb_pthat80_Pb-going_out/220106_053704/0000
       - [x] pthat > 120 GeV
         - p-going:  /ddesouza/Dijet_pThat-120_pPb-EmbEPOS_8p16_Pythia8/New_HiForest_pPb_PYTHIA8_EPOS_emb_pthat120_p-going_out/220106_053713/0000
         - Pb-going: /ddesouza/Dijet_pThat-120_PbP-EmbEPOS_8p16_Pythia8/New_HiForest_pPb_PYTHIA8_EPOS_emb_pthat120_Pb-going_out/220106_053722/0000
       - [x] pthat > 170 GeV
         - p-going:  /ddesouza/Dijet_pThat-170_pPb-EmbEPOS_8p16_Pythia8/New_HiForest_pPb_PYTHIA8_EPOS_emb_pthat170_p-going_out/220120_045548/0000
         - Pb-going: /ddesouza/Dijet_pThat-170_PbP-EmbEPOS_8p16_Pythia8/New_HiForest_pPb_PYTHIA8_EPOS_emb_pthat170_Pb-going_out/220120_045557/0000
       - [x] pthat > 220 GeV
         - p-going:  /ddesouza/Dijet_pThat-220_pPb-EmbEPOS_8p16_Pythia8/New_HiForest_pPb_PYTHIA8_EPOS_emb_pthat220_p-going_out/220106_053731/0000
         - Pb-going: /ddesouza/Dijet_pThat-220_PbP-EmbEPOS_8p16_Pythia8/New_HiForest_pPb_PYTHIA8_EPOS_emb_pthat220_Pb-going_out/220106_053740/0000
       - [x] pthat > 280 GeV
         - p-going:  /ddesouza/Dijet_pThat-280_pPb-EmbEPOS_8p16_Pythia8/New_HiForest_pPb_PYTHIA8_EPOS_emb_pthat280_p-going_out/220120_045606/0000
         - Pb-going: /ddesouza/Dijet_pThat-280_PbP-EmbEPOS_8p16_Pythia8/New_HiForest_pPb_PYTHIA8_EPOS_emb_pthat280_Pb-going_out/220120_045615/0000
       - [x] pthat > 370 GeV
         - p-going:  /ddesouza/Dijet_pThat-370_pPb-EmbEPOS_8p16_Pythia8/New_HiForest_pPb_PYTHIA8_EPOS_emb_pthat370_p-going_out/220106_053748/0000
         - Pb-going: /ddesouza/Dijet_pThat-370_PbP-EmbEPOS_8p16_Pythia8/New_HiForest_pPb_PYTHIA8_EPOS_emb_pthat370_Pb-going_out/220106_053757/0000
       - [x] pthat > 460 GeV  
         - p-going:  /ddesouza/Dijet_pThat-460_pPb-EmbEPOS_8p16_Pythia8/New_HiForest_pPb_PYTHIA8_EPOS_emb_pthat460_p-going_out/220120_045624/0000
         - Pb-going: /ddesouza/Dijet_pThat-460_PbP-EmbEPOS_8p16_Pythia8/New_HiForest_pPb_PYTHIA8_EPOS_emb_pthat460_Pb-going_out/220120_045633/0000
       - [x] pthat > 540 GeV
         - p-going:  /ddesouza/Dijet_pThat-540_pPb-EmbEPOS_8p16_Pythia8/New_HiForest_pPb_PYTHIA8_EPOS_emb_pthat540_p-going_out/220106_053806/0000
         - Pb-going: /ddesouza/Dijet_pThat-540_PbP-EmbEPOS_8p16_Pythia8/New_HiForest_pPb_PYTHIA8_EPOS_emb_pthat540_Pb-going_out/220106_053815/0000
      
2. Skim production  -> stored at CERN EOS (Dener and Abhishek folders, if you wanna access, just ask) -> Move to HIN EOS?
   - [ ] MB data
   - [ ] HM data
   - [ ] Jet data
   - [ ] MC -> started!

3. Histograms for observables:
