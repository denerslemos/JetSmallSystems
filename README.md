# Jet pPb analysis at 8.16 TeV

This branch contain relevant information about the data processing of pPb at 8.16 TeV dataset collected by CMS in the Run2 at November/December of 2016. In addition, the status and step-by-step usage of the codes are included as follows:

## Code structure and steps:

HiForest production -> Make the skims -> produce histograms -> run macros for plots

> HiForest
> > Setup for official HiForest setup. Intructions to add event plane informations are also included

> Skim
> > Produce the skims using HiForest as input. We can use CRAB3 or HTCondor to production and is useful to reduce the size of files.

> Histo
> > C++ code using ROOT framework to produce the histograms for analysis: Delta R, 2PC, ... . Mixing is done at this step.

> Macros
> > Codes using ROOT to produce the result plots, fits and so on for our analysis 

## Status:

1. HiForest production: Ongoing -> stored at T2_BR_SPRACE
   - Data
     - [ ] MB - ntrkoff -> [0,185]
     - [ ] HM - ntrkoff -> [185, 250] (for HM 1 to 6) and [250, 400] (for HM 7)
     - [x] Jet samples -> EP information not included
       - p-going:  /store/user/ddesouza/PAEGJet1/HiForest_pPb_8TeV_p-going_JetSamples_out/211211_161432/*
       - Pb-going: /store/user/ddesouza/PAEGJet1/HiForest_pPb_8TeV_Pb-going_JetSamples_out/211211_162021/*

   - MC simulations: Ongoing -> stored at T2_BR_SPRACE
     - [ ] EPOS MB
         - p-going: 
         - Pb-going:
         
     - [ ] HIJING MB
         - p-going: 
         - Pb-going:
         
     - [ ] AMPT MB
         - p-going: 
         - Pb-going:
         
     - [x] Pythia8 - Dijet - unembedded
       - [x] pthat > 15 GeV 
         - p-going:  /store/user/ddesouza/Dijet_pThat-15_pPb-Bst_8p16_Pythia8/New_HiForest_pPb_PYTHIA8_pthat15_p-going_out/220105_185751/0000
         - Pb-going: /store/user/ddesouza/Dijet_pThat-15_PbP-Bst_8p16_Pythia8/New_HiForest_pPb_PYTHIA8_pthat15_Pb-going_out/220105_190525/0000
       - [x] pthat > 30 GeV 
         - p-going:  /store/user/ddesouza/Dijet_pThat-30_pPb-Bst_8p16_Pythia8/New_HiForest_pPb_PYTHIA8_pthat30_p-going_out/220105_190608/0000
         - Pb-going: /store/user/ddesouza/Dijet_pThat-30_PbP-Bst_8p16_Pythia8/New_HiForest_pPb_PYTHIA8_pthat30_Pb-going_out/220105_190651/0000
       - [x] pthat > 50 GeV 
         - p-going:  /store/user/ddesouza/Dijet_pThat-50_pPb-Bst_8p16_Pythia8/New_HiForest_pPb_PYTHIA8_pthat50_p-going_out/220105_190734/0000
         - Pb-going: /store/user/ddesouza/Dijet_pThat-50_PbP-Bst_8p16_Pythia8/New_HiForest_pPb_PYTHIA8_pthat50_Pb-going_out/220105_190818/0000
       - [x] pthat > 80 GeV
         - p-going:  /store/user/ddesouza/Dijet_pThat-80_pPb-Bst_8p16_Pythia8/New_HiForest_pPb_PYTHIA8_pthat80_p-going_out/220105_190900/0000
         - Pb-going: /store/user/ddesouza/Dijet_pThat-80_PbP-Bst_8p16_Pythia8/New_HiForest_pPb_PYTHIA8_pthat80_Pb-going_out/220105_190943/0000
       - [x] pthat > 120 GeV 
         - p-going:  /store/user/ddesouza/Dijet_pThat-120_pPb-Bst_8p16_Pythia8/New_HiForest_pPb_PYTHIA8_pthat120_p-going_out/220105_191026/0000
         - Pb-going: /store/user/ddesouza/Dijet_pThat-120_PbP-Bst_8p16_Pythia8/New_HiForest_pPb_PYTHIA8_pthat120_Pb-going_out/220105_191109/0000     
       - [x] pthat > 220 GeV
         - p-going:  /store/user/ddesouza/Dijet_pThat-220_pPb-Bst_8p16_Pythia8/New_HiForest_pPb_PYTHIA8_pthat220_p-going_out/220105_191152/0000
         - Pb-going: /store/user/ddesouza/Dijet_pThat-220_PbP-Bst_8p16_Pythia8/New_HiForest_pPb_PYTHIA8_pthat220_Pb-going_out/220105_191234/0000     
       - [x] pthat > 370 GeV
         - p-going:  /store/user/ddesouza/Dijet_pThat-370_pPb-Bst_8p16_Pythia8/New_HiForest_pPb_PYTHIA8_pthat370_p-going_out/220105_191317/0000
         - Pb-going: /store/user/ddesouza/Dijet_pThat-370_PbP-Bst_8p16_Pythia8/New_HiForest_pPb_PYTHIA8_pthat370_Pb-going_out/220105_191400/0000
       - [x] pthat > 540 GeV
         - p-going:  /store/user/ddesouza/Dijet_pThat-540_pPb-Bst_8p16_Pythia8/New_HiForest_pPb_PYTHIA8_pthat540_p-going_out/220105_191443/0000
         - Pb-going: /store/user/ddesouza/Dijet_pThat-540_PbP-Bst_8p16_Pythia8/New_HiForest_pPb_PYTHIA8_pthat540_Pb-going_out/220105_191528/0000
      
     - [ ] Pythia8  - Dijet - embedded (using EPOS)
       - [ ] pthat > 15 GeV
         - p-going:  
         - Pb-going: 
       - [ ] pthat > 30 GeV 
         - p-going: 
         - Pb-going: 
       - [ ] pthat > 50 GeV
         - p-going: 
         - Pb-going:    
       - [ ] pthat > 80 GeV
         - p-going: 
         - Pb-going:    
       - [ ] pthat > 120 GeV
         - p-going: 
         - Pb-going: 
       - [ ] pthat > 220 GeV
         - p-going: 
         - Pb-going:   
       - [ ] pthat > 370 GeV
         - p-going: 
         - Pb-going:  
       - [ ] pthat > 540 GeV
         - p-going: 
         - Pb-going: 
      
2. Skim production: 
   - [ ] MB data
   - [ ] HM data
   - [ ] Jet data
   - [ ] MC -> started!

3. Histograms/observables:

## Advice for CMS users: 
### Add the following lines in your ~/.bashrc

Crab setup
```
source /cvmfs/cms.cern.ch/crab3/crab.sh
```

Useful for HTcondor jobs:
```
alias bigbird08='export _condor_SCHEDD_HOST="bigbird08.cern.ch" export _condor_CREDD_HOST="bigbird08.cern.ch"'
alias bigbird09='export _condor_SCHEDD_HOST="bigbird09.cern.ch" export _condor_CREDD_HOST="bigbird09.cern.ch"'
alias bigbird10='export _condor_SCHEDD_HOST="bigbird10.cern.ch" export _condor_CREDD_HOST="bigbird10.cern.ch"'
alias bigbird11='export _condor_SCHEDD_HOST="bigbird11.cern.ch" export _condor_CREDD_HOST="bigbird11.cern.ch"'
alias bigbird12='export _condor_SCHEDD_HOST="bigbird12.cern.ch" export _condor_CREDD_HOST="bigbird12.cern.ch"'
alias bigbird13='export _condor_SCHEDD_HOST="bigbird13.cern.ch" export _condor_CREDD_HOST="bigbird13.cern.ch"'
alias bigbird14='export _condor_SCHEDD_HOST="bigbird14.cern.ch" export _condor_CREDD_HOST="bigbird14.cern.ch"'
alias bigbird15='export _condor_SCHEDD_HOST="bigbird15.cern.ch" export _condor_CREDD_HOST="bigbird15.cern.ch"'
alias bigbird16='export _condor_SCHEDD_HOST="bigbird16.cern.ch" export _condor_CREDD_HOST="bigbird16.cern.ch"'
alias bigbird17='export _condor_SCHEDD_HOST="bigbird17.cern.ch" export _condor_CREDD_HOST="bigbird17.cern.ch"'
alias bigbird18='export _condor_SCHEDD_HOST="bigbird18.cern.ch" export _condor_CREDD_HOST="bigbird18.cern.ch"'
alias bigbird19='export _condor_SCHEDD_HOST="bigbird19.cern.ch" export _condor_CREDD_HOST="bigbird19.cern.ch"'

alias condstat='condor_status -schedd' 
```
### Useful xrootd commands

To copy files for your local machine use xrdcp, example
```
xrdcp -d 1 -f root://cmsxrootd.fnal.gov//store/user/ddesouza/PAEGJet1/HiForest_pPb_8TeV_p-going_JetSamples_out/211211_161432/0000/HiForestAOD_1.root . &> out.txt &
```

To access files and create a list of files you can use xrdfs, example:
```
xrdfs root://cmsxrootd.fnal.gov ls /store/user/ddesouza/PAEGJet1/HiForest_pPb_8TeV_p-going_JetSamples_out/211211_161432/0000/ &> listofforestfiles.txt &
```
