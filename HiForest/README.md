#HiForest Setup

For pPb at 8.16 TeV the CMSSW version 8_0_28 must be used:

```
# Setup scram version
cmsrel CMSSW_8_0_28
cd CMSSW_8_0_28/src
cmsenv
git cms-merge-topic -u CmsHI:forest_CMSSW_8_0_28
# Switch to the branch HEAD
git remote add cmshi git@github.com:CmsHI/cmssw.git
git fetch cmshi --no-tags
git checkout -b forest_CMSSW_8_0_28 remotes/cmshi/forest_CMSSW_8_0_28
scram build -j4
cd HeavyIonsAnalysis/JetAnalysis/test/
./runtest.sh
```

