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
     - [x] MB - Ntrkoff -> range [0,185] -> It has more statistics than HM0 in the range [120, 185] :)
       - p-going: 
         - [x] ```/ddesouza/PAMinimumBias1/HeavyIon_Forest_pPb_8p16TeV_pgoing_Trigger_MB_PD1/220413_170920/*```
         - [x] ```/ddesouza/PAMinimumBias2/HeavyIon_Forest_pPb_8p16TeV_pgoing_Trigger_MB_PD2/220413_171031/*```
         - [x] ```/caber/PAMinimumBias3/HeavyIon_Forest_pPb_8p16TeV_pgoing_Trigger_MB_PD3/220413_201132/*```
         - [x] ```/caber/PAMinimumBias4/HeavyIon_Forest_pPb_8p16TeV_pgoing_Trigger_MB_PD4/220413_201343/*```
         - [x] ```/ddesouza/PAMinimumBias5/HeavyIon_Forest_pPb_8p16TeV_pgoing_Trigger_MB_PD5/220420_162052/*```
         - [x] ```/ddesouza/PAMinimumBias6/HeavyIon_Forest_pPb_8p16TeV_pgoing_Trigger_MB_PD6/220420_162808/*```
         - [x] ```/ahingraj/PAMinimumBias7/HeavyIon_Forest_pPb_8p16TeV_pgoing_Trigger_MB_PD7/220425_173932/*```
         - [x] ```/ahingraj/PAMinimumBias8/HeavyIon_Forest_pPb_8p16TeV_pgoing_Trigger_MB_PD8/220425_174127/*```
       - Pb-going:
         - [x] ```/caber/PAMinimumBias1/HeavyIon_Forest_pPb_8p16TeV_Pbgoing_Trigger_MB_PD1/220524_193354/*```
         - [x] ```/caber/PAMinimumBias2/HeavyIon_Forest_pPb_8p16TeV_Pbgoing_Trigger_MB_PD2/220524_193533/*```
         - [x] ```/sdogra/PAMinimumBias3/HeavyIon_Forest_pPb_8p16TeV_Pbgoing_Trigger_MB_PD3/220525_022016/*```
         - [x] ```/sdogra/PAMinimumBias4/HeavyIon_Forest_pPb_8p16TeV_Pbgoing_Trigger_MB_PD4/220713_015613/*```
         - [x] ```/ddesouza/PAMinimumBias5/HeavyIon_Forest_pPb_8p16TeV_Pbgoing_Trigger_MB_PD5/220702_174146/*```
         - [x] ```/ddesouza/PAMinimumBias6/HeavyIon_Forest_pPb_8p16TeV_Pbgoing_Trigger_MB_PD6/220723_150420/*```
         - [x] ```/caber/PAMinimumBias7/HeavyIon_Forest_pPb_8p16TeV_Pbgoing_Trigger_MB_PD7/220728_211425/*```
         - [x] ```/ahingraj/PAMinimumBias8/HeavyIon_Forest_pPb_8p16TeV_Pbgoing_Trigger_MB_PD8/220626_201229/*```
         - [x] ```/caber/PAMinimumBias9/HeavyIon_Forest_pPb_8p16TeV_Pbgoing_Trigger_MB_PD9/220705_154359/*```
         - [x] ```/ahingraj/PAMinimumBias10/HeavyIon_Forest_pPb_8p16TeV_Pbgoing_Trigger_MB_PD10/220719_152717/*```
         - [x] ```/ddesouza/PAMinimumBias11/HeavyIon_Forest_pPb_8p16TeV_Pbgoing_Trigger_MB_PD11/220718_162751/*```
         - [x] ```/caber/PAMinimumBias12/HeavyIon_Forest_pPb_8p16TeV_Pbgoing_Trigger_MB_PD12/220626_192407/*```
         - [x] ```/ddesouza/PAMinimumBias13/HeavyIon_Forest_pPb_8p16TeV_Pbgoing_Trigger_MB_PD13/220626_183646/*```
         - [x] ```/ahingraj/PAMinimumBias14/HeavyIon_Forest_pPb_8p16TeV_Pbgoing_Trigger_MB_PD14/220705_160434/*```
         - [x] ```/ddesouza/PAMinimumBias15/HeavyIon_Forest_pPb_8p16TeV_Pbgoing_Trigger_MB_PD15/220524_161505/*```
         - [x] ```/ddesouza/PAMinimumBias16/HeavyIon_Forest_pPb_8p16TeV_Pbgoing_Trigger_MB_PD16/220524_161140/*```
         - [x] ```/ahingraj/PAMinimumBias17/HeavyIon_Forest_pPb_8p16TeV_Pbgoing_Trigger_MB_PD17/220524_161145/*```
         - [x] ```/ahingraj/PAMinimumBias18/HeavyIon_Forest_pPb_8p16TeV_Pbgoing_Trigger_MB_PD18/220524_161301/*```
         - [x] ```/borzari/PAMinimumBias19/HeavyIon_Forest_pPb_8p16TeV_Pbgoing_Trigger_MB_PD19/220426_135622/*```
         - [x] ```/ahingraj/PAMinimumBias20/HeavyIon_Forest_pPb_8p16TeV_Pbgoing_Trigger_MB_PD20/220727_150022/*```
     - [x] HM - Ntrkoff -> range [185, 250] (PD's 1 to 6)
       - p-going: 
         - [x] ```/ddesouza/PAHighMultiplicity1/HeavyIon_Forest_pPb_8p16TeV_pgoing_Trigger_HM185_PD1/220326_030954/*```
         - [x] ```/ddesouza/PAHighMultiplicity2/HeavyIon_Forest_pPb_8p16TeV_pgoing_Trigger_HM185_PD2/220326_031425/*```
         - [x] ```/borzari/PAHighMultiplicity3/HeavyIon_Forest_pPb_8p16TeV_pgoing_Trigger_HM185_PD3/220326_152218/*```
         - [x] ```/borzari/PAHighMultiplicity4/HeavyIon_Forest_pPb_8p16TeV_pgoing_Trigger_HM185_PD4/220326_152246/*```
         - [x] ```/caber/PAHighMultiplicity5/HeavyIon_Forest_pPb_8p16TeV_pgoing_Trigger_HM185_PD5/220326_182617/*```
         - [x] ```/caber/PAHighMultiplicity6/HeavyIon_Forest_pPb_8p16TeV_pgoing_Trigger_HM185_PD6/220326_182730/*```
       - Pb-going:
         - [x] ```/ahingraj/PAHighMultiplicity1/HeavyIon_Forest_pPb_8p16TeV_Pbgoing_Trigger_HM185_PD1/220327_002010/*```
         - [x] ```/ahingraj/PAHighMultiplicity2/HeavyIon_Forest_pPb_8p16TeV_Pbgoing_Trigger_HM185_PD2/220327_002150/*```
         - [x] ```/ddesouza/PAHighMultiplicity3/HeavyIon_Forest_pPb_8p16TeV_Pbgoing_Trigger_HM185_PD3/220508_173510/*```
         - [x] ```/ddesouza/PAHighMultiplicity4/HeavyIon_Forest_pPb_8p16TeV_Pbgoing_Trigger_HM185_PD4/220508_173553/*```
         - [x] ```/ddesouza/PAHighMultiplicity5/HeavyIon_Forest_pPb_8p16TeV_Pbgoing_Trigger_HM185_PD5/220401_154028/*```
         - [x] ```/ddesouza/PAHighMultiplicity6/HeavyIon_Forest_pPb_8p16TeV_Pbgoing_Trigger_HM185_PD6/220401_154217/*```
     - [x] HM - Ntrkoff -> range [250, inf] (PD 7)
       - p-going: ```/ddesouza/PAHighMultiplicity7/HeavyIon_Forest_pPb_8p16TeV_pgoing_Trigger_HM250/220327_024216/*```
       - Pb-going: ```/ddesouza/PAHighMultiplicity7/HeavyIon_Forest_pPb_8p16TeV_Pbgoing_Trigger_HM250/220327_024248/*```
     - [x] Jet samples -> EP information not included
       - p-going:  ```/ddesouza/PAEGJet1/HeavyIon_Forest_pPb_8p16TeV_Pbgoing_Trigger_Jets_out/220807_190949/*```
       - Pb-going: ```/ddesouza/PAEGJet1/HeavyIon_Forest_pPb_8p16TeV_Pbgoing_Trigger_Jets_out/220807_190949/*```

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
         - p-going:  
         - ```/ahingraj/Dijet_pThat-15_pPb-Bst_8p16_Pythia8/HeavyIon_Forest_pPb_8p16TeV_pgoing_PYTHIA8_Unembedded_pthat15_out/220808_162221/0000```
         - Pb-going: 
         - ```/ahingraj/Dijet_pThat-15_PbP-Bst_8p16_Pythia8/HeavyIon_Forest_pPb_8p16TeV_Pbgoing_PYTHIA8_Unembedded_pthat15_out/220809_170405/0000```
       - [x] pthat > 30 GeV 
         - p-going:  
         - ```/ahingraj/Dijet_pThat-30_pPb-Bst_8p16_Pythia8/HeavyIon_Forest_pPb_8p16TeV_pgoing_PYTHIA8_Unembedded_pthat30_out/220808_162243/0000```
         - Pb-going: 
         - ```/ahingraj/Dijet_pThat-30_PbP-Bst_8p16_Pythia8/HeavyIon_Forest_pPb_8p16TeV_Pbgoing_PYTHIA8_Unembedded_pthat30_out/220809_170421/0000```
       - [x] pthat > 50 GeV 
         - p-going:  
         - ```/ahingraj/Dijet_pThat-50_pPb-Bst_8p16_Pythia8/HeavyIon_Forest_pPb_8p16TeV_pgoing_PYTHIA8_Unembedded_pthat50_out/220808_162305/0000```
         - Pb-going: 
         - ```/ahingraj/Dijet_pThat-50_PbP-Bst_8p16_Pythia8/HeavyIon_Forest_pPb_8p16TeV_Pbgoing_PYTHIA8_Unembedded_pthat50_out/220809_170437/0000```
       - [x] pthat > 80 GeV
         - p-going:  
         - ```/ahingraj/Dijet_pThat-80_pPb-Bst_8p16_Pythia8/HeavyIon_Forest_pPb_8p16TeV_pgoing_PYTHIA8_Unembedded_pthat80_out/220808_162326/0000```
         - Pb-going: 
         - ```/ahingraj/Dijet_pThat-80_PbP-Bst_8p16_Pythia8/HeavyIon_Forest_pPb_8p16TeV_Pbgoing_PYTHIA8_Unembedded_pthat80_out/220809_170452/0000```
       - [x] pthat > 120 GeV 
         - p-going:  
         - ```/ahingraj/Dijet_pThat-120_pPb-Bst_8p16_Pythia8/HeavyIon_Forest_pPb_8p16TeV_pgoing_PYTHIA8_Unembedded_pthat120_out/220808_162348/0000```
         - Pb-going: 
         - ```/ahingraj/Dijet_pThat-120_PbP-Bst_8p16_Pythia8/HeavyIon_Forest_pPb_8p16TeV_Pbgoing_PYTHIA8_Unembedded_pthat120_out/220809_170508/0000```
       - [x] pthat > 170 GeV      
         - p-going:  
         - ```/ahingraj/Dijet_pThat-170_pPb-Bst_8p16_Pythia8/HeavyIon_Forest_pPb_8p16TeV_pgoing_PYTHIA8_Unembedded_pthat170_out/220808_162425/0000```
         - Pb-going: 
         - ```/ahingraj/Dijet_pThat-170_PbP-Bst_8p16_Pythia8/HeavyIon_Forest_pPb_8p16TeV_Pbgoing_PYTHIA8_Unembedded_pthat170_out/220809_170523/0000```
       - [x] pthat > 220 GeV
         - p-going:  
         - ```/ahingraj/Dijet_pThat-220_pPb-Bst_8p16_Pythia8/HeavyIon_Forest_pPb_8p16TeV_pgoing_PYTHIA8_Unembedded_pthat220_out/220808_162445/0000```
         - Pb-going: 
         - ```/ahingraj/Dijet_pThat-220_PbP-Bst_8p16_Pythia8/HeavyIon_Forest_pPb_8p16TeV_Pbgoing_PYTHIA8_Unembedded_pthat220_out/220809_170538/0000```   
       - [x] pthat > 280 GeV
         - p-going:  
         - ```/ahingraj/Dijet_pThat-280_pPb-Bst_8p16_Pythia8/HeavyIon_Forest_pPb_8p16TeV_pgoing_PYTHIA8_Unembedded_pthat280_out/220808_162507/0000```
         - Pb-going: 
         - ```/ahingraj/Dijet_pThat-280_PbP-Bst_8p16_Pythia8/HeavyIon_Forest_pPb_8p16TeV_Pbgoing_PYTHIA8_Unembedded_pthat280_out/220809_170553/0000```
       - [x] pthat > 370 GeV
         - p-going:  
         - ```/ahingraj/Dijet_pThat-370_pPb-Bst_8p16_Pythia8/HeavyIon_Forest_pPb_8p16TeV_pgoing_PYTHIA8_Unembedded_pthat370_out/220808_162526/0000```
         - Pb-going: 
         - ```/ahingraj/Dijet_pThat-370_PbP-Bst_8p16_Pythia8/HeavyIon_Forest_pPb_8p16TeV_Pbgoing_PYTHIA8_Unembedded_pthat370_out/220809_170611/0000
       - [x] pthat > 460 GeV
         - p-going:  
         - ```/ahingraj/Dijet_pThat-460_pPb-Bst_8p16_Pythia8/HeavyIon_Forest_pPb_8p16TeV_pgoing_PYTHIA8_Unembedded_pthat460_out/220808_162547/0000```
         - Pb-going: 
         - ```/ahingraj/Dijet_pThat-460_PbP-Bst_8p16_Pythia8/HeavyIon_Forest_pPb_8p16TeV_Pbgoing_PYTHIA8_Unembedded_pthat460_out/220809_170627/0000```
       - [x] pthat > 540 GeV
         - p-going:  
         - ```/ahingraj/Dijet_pThat-540_pPb-Bst_8p16_Pythia8/HeavyIon_Forest_pPb_8p16TeV_pgoing_PYTHIA8_Unembedded_pthat540_out/220808_162607/0000```
         - Pb-going: 
         - ```/ahingraj/Dijet_pThat-540_PbP-Bst_8p16_Pythia8/HeavyIon_Forest_pPb_8p16TeV_Pbgoing_PYTHIA8_Unembedded_pthat540_out/220809_170642/0000```
      
     - [x] Pythia8  - Dijet - embedded (using EPOS) - EP information not included
       - [x] pthat > 15 GeV
         - p-going:   
         - Pb-going: 
       - [x] pthat > 30 GeV 
         - p-going: 
         - Pb-going: 
       - [x] pthat > 50 GeV
         - p-going:  
         - Pb-going: 
       - [x] pthat > 80 GeV
         - p-going: 
         - Pb-going:
       - [x] pthat > 120 GeV
         - p-going:  
         - Pb-going:
       - [x] pthat > 170 GeV
         - p-going:  
         - Pb-going:
       - [x] pthat > 220 GeV
         - p-going:  
         - Pb-going:
       - [x] pthat > 280 GeV
         - p-going:  
         - Pb-going:
       - [x] pthat > 370 GeV
         - p-going:  
         - Pb-going:
       - [x] pthat > 460 GeV  
         - p-going: 
         - Pb-going:
       - [x] pthat > 540 GeV
         - p-going:
         - Pb-going:
      
2. Skim production  -> stored at CERN EOS (Dener and Abhishek folders, if you wanna access, just ask) -> Move to HIN EOS?
   - [ ] MB data
   - [ ] HM data
   - [ ] Jet data
   - [ ] MC -> started!

3. Histograms for observables:
