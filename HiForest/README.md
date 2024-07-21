# HiForest Setup


For pPb at 8.16 TeV the CMSSW version 8_0_28 must be used (based on https://twiki.cern.ch/twiki/bin/viewauth/CMS/HiForestSetup#Setup_for_8_0_28):

```
#Moving to container
cmssw-el7
#VOMS
voms-proxy-init -rfc -voms cms
# Setup CMSSW version
export SCRAM_ARCH=slc7_amd64_gcc530
cmsrel CMSSW_8_0_28
cd CMSSW_8_0_28/src
cmsenv
git cms-merge-topic -u CmsHI:forest_CMSSW_8_0_28
# Switch to the branch HEAD
git remote add cmshi git@github.com:CmsHI/cmssw.git
git fetch cmshi --no-tags
git checkout -b forest_CMSSW_8_0_28 remotes/cmshi/forest_CMSSW_8_0_28
cmsenv
# Dener's changes
cp /afs/cern.ch/work/d/ddesouza/public/ForForest/TrackAnalyzer.cc $CMSSW_BASE/src/HeavyIonsAnalysis/TrackAnalysis/src/
cp /afs/cern.ch/work/d/ddesouza/public/ForForest/trackAnalyzer_cfi.py $CMSSW_BASE/src/HeavyIonsAnalysis/TrackAnalysis/python/
cp /afs/cern.ch/work/d/ddesouza/public/ForForest/HiEvtAnalyzer.cc $CMSSW_BASE/src/HeavyIonsAnalysis/EventAnalysis/
cp /afs/cern.ch/work/d/ddesouza/public/ForForest/METAnalyzer.cc $CMSSW_BASE/src/HeavyIonsAnalysis/TrackAnalysis/src/
cp /afs/cern.ch/work/d/ddesouza/public/ForForest/METAnalyzer*.py $CMSSW_BASE/src/HeavyIonsAnalysis/TrackAnalysis/python/
cp /afs/cern.ch/work/d/ddesouza/public/ForForest/HiGenAnalyzer_cfi.py $CMSSW_BASE/src/HeavyIonsAnalysis/JetAnalysis/python/ 
cp /afs/cern.ch/work/d/ddesouza/public/ForForest/HiSignalGenJetProducer.cc $CMSSW_BASE/src/RecoHI/HiJetAlgos/plugins/
# Include event plane information -> Need to adapt event plane code from: 
# https://twiki.cern.ch/twiki/bin/viewauth/CMS/SWGuideHeavyIonFlatEvtPlane#CMSSW_8_0_24_Instructions_2016_p
# To make it easy you can just copy those folders:
cp -r /afs/cern.ch/work/d/ddesouza/public/ForForest/CondFormats $CMSSW_BASE/src/
cp -r /afs/cern.ch/work/d/ddesouza/public/ForForest/HiEvtPlaneAlgos $CMSSW_BASE/src/RecoHI/
cp -r /afs/cern.ch/work/d/ddesouza/public/ForForest/HiEvtPlaneCalib $CMSSW_BASE/src/HeavyIonsAnalysis/
cp -r /afs/cern.ch/work/d/ddesouza/public/ForForest/QWNtrkOfflineProducer $CMSSW_BASE/src/HeavyIonsAnalysis/
cp -r /afs/cern.ch/work/d/ddesouza/public/ForForest/VNAnalysis $CMSSW_BASE/src/HeavyIonsAnalysis/
cp -r /afs/cern.ch/work/d/ddesouza/public/ForForest/workstation $CMSSW_BASE/src/HeavyIonsAnalysis/JetAnalysis/test/
# Now compile and test
scram build -j10
cd HeavyIonsAnalysis/JetAnalysis/test/
./runtest.sh
# Once tests are done, go to:
cd $CMSSW_BASE/src/HeavyIonsAnalysis/JetAnalysis/test/workstation
#for quick test go to quickcheck folder and run 
cd quickcheck
cmsRun runForestAOD_pPb_DATA_80X.py &> out.txt &
```
Each folder inside of ```workstation``` contain the crab configuration files to submit for different datasets. You do not need to change anything. Do not run for MC yet (will be updated soon).
To submit crab jobs you just need to use the following command (after the VOMS command):
```
python crab_file.py
```
The Forest root output files will be stored at SPRACE/Brazil.
