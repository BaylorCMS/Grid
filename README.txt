Grid
====
This is where I store all grid related packages.

source ~cmssoft/shrc
cmsrel CMSSW_7_4_1
cd CMSSW_7_4_1/src
cmsenv
git clone git@github.com:BaylorCMS/Grid.git
cd Grid/
cd CrabTestPackage/
source cmsDriver_commands.sh 

crab -cfg crab_WE_7TeV_pbs.cfg -create -submit
crab -cfg crab_slurp_pbs.cfg   -create -submit

source /cvmfs/cms.cern.ch/crab3/crab.sh
crab submit crab3Config_WE_7TeV.py
crab submit crab3Config_slurp.py
