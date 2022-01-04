# pPb at 8.16 TeV

This branch contain relevant information about the data processing of pPb at 8.16 TeV dataset collected by CMS in the Run2 at November/December of 2016. In addition, the status and step-by-step usage of the codes are included as follows:

## codes:

> HiForest setup


## steps/status:

1. HiForest prodution: Ongoing
   - Data
     - [ ] MB
     - [ ] HM
     - [x] Jet

   - MC simulations
     - [ ] EPOS MB
     - [ ] HIJING MB
     - [ ] AMPT MB
     - [ ] Pythia8
       - [ ] pthat > 15 GeV 

2. Skim production: 
   - [ ] MB data
   - [ ] HM data
   - [ ] Jet data
   - [ ] MC

3. Histograms/observables:

## advice for CMS users: add the following lines in your ~/.bashrc

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
