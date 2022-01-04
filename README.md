# pPb at 8.16 TeV

This branch contain relevant information about the data processing of pPb at 8.16 TeV dataset collected by CMS in the Run2 at November/December of 2016. In addition, the status and step-by-step usage of the codes are included as follows:

## codes:

> HiForest setup


## steps/status:

1. HiForest production: Ongoing -> stored at T2_BR_SPRACE
   - Data
     - [ ] MB
     - [ ] HM
     - [x] Jet -> do not include EP information
       - p-going:  /store/user/ddesouza/PAEGJet1/HiForest_pPb_8TeV_p-going_JetSamples_out/211211_161432/000*
       - Pb-going: /store/user/ddesouza/PAEGJet1/HiForest_pPb_8TeV_Pb-going_JetSamples_out/211211_162021/000*

   - MC simulations: Ongoing -> stored at T2_BR_SPRACE
     - [ ] EPOS MB
     - [ ] HIJING MB
     - [ ] AMPT MB
     - [ ] Pythia8 -> unembedded
       - [x] pthat > 15 GeV 
         - p-going:  /store/user/ahingraj/Dijet_pThat-15_pPb-EmbEPOS_8p16_Pythia8/HiForest_pPb_PYTHIA8_pthat15_emb_p-going_out/211221_222018/0000/
         - Pb-going: /store/user/ahingraj/Dijet_pThat-15_PbP-EmbEPOS_8p16_Pythia8/HiForest_pPb_PYTHIA8_pthat15_emb_Pb-going_out/211221_222028/0000/
       - [ ] pthat > 30 GeV 
       - [ ] pthat > 50 GeV 
       - [ ] pthat >  GeV 
       - [ ] pthat >  GeV 
       - [ ] pthat >  GeV 
       - [ ] pthat >  GeV 
       - [ ] pthat >  GeV 
     - [ ] Pythia8 -> embedded
       - [x] pthat > 15 GeV
         - p-going:  /store/user/ahingraj/Dijet_pThat-15_pPb-EmbEPOS_8p16_Pythia8/HiForest_pPb_PYTHIA8_pthat15_emb_p-going_out/211221_222018/0000/
         - Pb-going: /store/user/ahingraj/Dijet_pThat-15_PbP-EmbEPOS_8p16_Pythia8/HiForest_pPb_PYTHIA8_pthat15_emb_Pb-going_out/211221_222028/0000/
       - [ ] pthat > 30 GeV 
       - [ ] pthat > 50 GeV 
       - [ ] pthat >  GeV 
       - [ ] pthat >  GeV 
       - [ ] pthat >  GeV 
       - [ ] pthat >  GeV 
       - [ ] pthat >  GeV 

2. Skim production: 
   - [ ] MB data
   - [ ] HM data
   - [ ] Jet data
   - [ ] MC

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
xrdcp -d 1 -f root://cmsxrootd.fnal.gov//store/user/ddesouza/PAEGJet1/HiForest_pPb_8TeV_JetsA_out/211210_061724/0000/HiForestAOD_1.root . &> out.txt &
```

To access files and create a list of files you can use xrdfs, example:
```
xrdfs root://cmsxrootd.fnal.gov ls /store/user/ddesouza/PAEGJet1/HiForest_pPb_8TeV_p-going_JetSamples_out/211211_161432/0000/ &> listofforestfiles.txt &
```
