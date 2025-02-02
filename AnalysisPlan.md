# Analysis Plan

### ~Completed:

Preliminary cut-based signal and background yields estimate 
 - using a coarse-grained grid search on pT, msd, and tagger scores
 - 2017 lumi + data only
 - measured for two AK8 fat jets, two AK15 fat jets, and a hybrid (AK8 for bb candidate, AK15 for VV candidate)
 - background estimation from data sidebands
 - with AK8 and AK15 mass-decorrelated ParticleNet Hbb taggers + NOT mass-decorrelated AK8 ParticleNet H4q tagger

Trigger scale factor measurements:
 - Measured for AK8, AK15, and hybrid jets, single-jet 2D (mass, pT binned) efficiencies (applied assuming prob. of each fat jet passing trigger is independent) and 3D (jet 1 mass, jet 1 pt, jet 2 pt binned)  efficiencies ([processors](https://github.com/rkansal47/HHbbVV/blob/main/processors/JetHTTriggerEfficienciesProcessor.py))
 - Tentatively decided to use hybrid case which gave the highest preselection yield and should increase with a better HWW tagger 


### In progress

1) HWW tagger + mass regression development ([Zichun's tagger repo](https://github.com/zichunhao/weaver) and [Ish's regression repo](https://github.com/ikaul00/weaver))

2) AN write-up https://gitlab.cern.ch/tdr/notes/AN-21-126

3) Processor for skimming nano files
 - draft of skimmer https://github.com/rkansal47/HHbbVV/blob/main/processors/bbVVSkimmer.py, issues right now running on coffea-casa
 - TODOs:
   - UL pileup weight calculation
   - apply trigger SFs 
   - hybrid case sorting

4) Hybrid SFs
 - use 2017 Run B data as well
 - consistent hybrid policy
 - settle on 2D trigger SFs

5) Porting the cutting and plotting from this nightmare https://github.com/rkansal47/boostedhiggs/blob/master/binder/plot_test.py into something that is readable by humans


#### Samples

Currently have for UL 2017:

 - Data: JetHT RunB-F
 - QCD HT 300-inf
 - TT hadronic, TT semileptonic, T Mtt
 - ST s-channel leptonic, ST t-channel, Inclusive, ST tW top + antitop no fully hadronic
 - ggF HWW inclusive
 - VV, V+jets

1) Requesting UL samples
    - Requesting HH signal samples ggF and VBF for bbWW all-hadronic
    - TODO: Request UL ggH (and VBF?) signal samples for HtoWW inclusive

2) Need to use `RunIISummer20UL17` in PFNano for next production


### TODO:

1) BDT
    - Choose and plot potential BDT variables
    - Train a basic BDT, compare signal efficiency to cut-based analysis, decide whether to continue

2) Background estimation...


