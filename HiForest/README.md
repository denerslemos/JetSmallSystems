# HiForest Setup

For pPb at 8.16 TeV the CMSSW version 8_0_28 must be used:

```
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
# Dener's changes
cp /afs/cern.ch/work/d/ddesouza/public/ForForest/TrackAnalyzer.cc $CMSSW_BASE/src/HeavyIonsAnalysis/TrackAnalysis/src/
cp /afs/cern.ch/work/d/ddesouza/public/ForForest/METAnalyzer.cc $CMSSW_BASE/src/HeavyIonsAnalysis/TrackAnalysis/src/
cp /afs/cern.ch/work/d/ddesouza/public/ForForest/METAnalyzer*.py $CMSSW_BASE/src/HeavyIonsAnalysis/TrackAnalysis/python/
cp /afs/cern.ch/work/d/ddesouza/public/ForForest/HiGenAnalyzer_cfi.py $CMSSW_BASE/src/HeavyIonsAnalysis/JetAnalysis/python/ 
# Include event plane information -> Need to adapt event plane code from: 
# https://twiki.cern.ch/twiki/bin/viewauth/CMS/SWGuideHeavyIonFlatEvtPlane#CMSSW_8_0_24_Instructions_2016_p
# To make it easy you can just copy those folders:
cp -r /afs/cern.ch/work/d/ddesouza/public/ForForest/CondFormats $CMSSW_BASE/src/
cp -r /afs/cern.ch/work/d/ddesouza/public/ForForest/EPfiles $CMSSW_BASE/src/
cp -r /afs/cern.ch/work/d/ddesouza/public/ForForest/HiEvtPlaneAlgos $CMSSW_BASE/src/RecoHI/
cp -r /afs/cern.ch/work/d/ddesouza/public/ForForest/HiEvtPlaneCalib $CMSSW_BASE/src/HeavyIonsAnalysis/
cp -r /afs/cern.ch/work/d/ddesouza/public/ForForest/QWNtrkOfflineProducer $CMSSW_BASE/src/RecoHI/
cp -r /afs/cern.ch/work/d/ddesouza/public/ForForest/VNAnalysis $CMSSW_BASE/src/RecoHI/
# Now compile and test
scram build -j4
cd HeavyIonsAnalysis/JetAnalysis/test/
./runtest.sh
# Once tests are done use the files added here for each case of interest. Download it as:
```
