TrackTree
=========

.. _tracktree:

Source code can be found here: https://github.com/imawby/LArContent/blob/feature/Metrics/larpandoracontent/LArMetrics/TrackValidationTool.cc
Plotting script can be found here: https://github.com/imawby/PandoraMetrics/blob/main/TrackValidation.ipynb

Branches had several pre-fixes:

- MCP = variables that belong to the target MCParticle
- BM = variables that belong to the best-matched PFO
  
.. csv-table::
   :header: "Branch Name", "Type", "Description", "Default/Special Values"
   :widths: 15, 10, 30, 10

   "Run", "int", "Run number", ""
   "Subrun", "int", "Subrun number", ""
   "Event", "int", "Event number", ""
   "BM_EndpointX", "std::vector<float>", "x-coordinate of the reco endpoint obtained from a sliding fit [cm]", "-9999.f if no reco or if fit fails"
   "BM_EndpointY", "std::vector<float>", "y-coordinate of the reco endpoint obtained from a sliding fit [cm]", "-9999.f if no reco or if fit fails"
   "BM_EndpointZ", "std::vector<float>", "z-coordinate of the reco endpoint obtained from a sliding fit [cm]", "-9999.f if no reco or if fit fails"
   "BM_EndpointAcc", "std::vector<float>", "signed true-reco endpoint separation (+ve = downstream, -ve = upstream) [cm]", "-9999.f if no reco or if fit fails"
   "BM_StartDirX", "std::vector<float>", "x-component of the initial direction obtained from a sliding fit [cm]", "-9999.f if no reco or if fit fails"
   "BM_StartDirY", "std::vector<float>", "y-component of the initial direction obtained from a sliding fit [cm]", "-9999.f if no reco or if fit fails"
   "BM_StartDirZ", "std::vector<float>", "z-component of the initial direction obtained from a sliding fit [cm]", "-9999.f if no reco or if fit fails"
   "BM_StartDirAcc", "std::vector<float>", "opening angle between true and reco initial directions [radians]", "-9999.f if no reco or if fit fails"
   "BM_EndDirX", "std::vector<float>", "x-component of the end direction obtained from a sliding fit [cm]", "-9999.f if no reco or if fit fails"
   "BM_EndDirY", "std::vector<float>", "y-component of the end direction obtained from a sliding fit [cm]", "-9999.f if no reco or if fit fails"
   "BM_EndDirZ", "std::vector<float>", "z-component of the end direction obtained from a sliding fit [cm]", "-9999.f if no reco or if fit fails"            
   "BM_EndDirAcc", "std::vector<float>", "opening angle between true and reco end directions [radians]", "-9999.f if no reco or if fit fails"
   "BM_IsCorrectOrientation", "std::vector<int>", "whether the vertex and endpoint are the correct way around", "-1 if no reco or if fit fails"      
   "MCP_IsLeaving", "std::vector<int>", "whether the MCParticle endpoint is within 5cm of the detector walls", ""
   "MCP_EndpointMCHits", "std::vector<int>", "number of 2D MCParticle hits that lie in the 5cm preceeding the MCParticle endpoint", "-1.f if MCParticle has zero momentum at the penultimate trajectory point"
   "MCP_EndpointMCHitsU", "std::vector<int>", "number of U-view MCParticle hits that lie in the 5cm preceeding the MCParticle endpoint", "-1.f if MCParticle has zero momentum at the penultimate trajectory point"
   "MCP_EndpointMCHitsV", "std::vector<int>", "number of V-view MCParticle hits that lie in the 5cm preceeding the MCParticle endpoint", "-1.f if MCParticle has zero momentum at the penultimate trajectory point"
   "MCP_EndpointMCHitsW", "std::vector<int>", "number of W-view MCParticle hits that lie in the 5cm preceeding the MCParticle endpoint", "-1.f if MCParticle has zero momentum at the penultimate trajectory point"
   "MCP_EndpointPfoHits", "std::vector<int>", "number of 2D PFO hits that lie in the 5cm preceeding the MCParticle endpoint", "-1.f if MCParticle has zero momentum at the penultimate trajectory point"
   "MCP_EndpointPfoHitsU", "std::vector<int>", "number of U-view PFO hits that lie in the 5cm preceeding the MCParticle endpoint", "-1.f if MCParticle has zero momentum at the penultimate trajectory point"
   "MCP_EndpointPfoHitsV", "std::vector<int>", "number of V-view PFO hits that lie in the 5cm preceeding the MCParticle endpoint", "-1.f if MCParticle has zero momentum at the penultimate trajectory point"
   "MCP_EndpointPfoHitsW", "std::vector<int>", "number of W-view PFO hits that lie in the 5cm preceeding the MCParticle endpoint", "-1.f if MCParticle has zero momentum at the penultimate trajectory point"
   "MCP_EndpointCompleteness", "std::vector<double>", "completeness of the 5cm region that preceeds the MCParticle endpoint", "-1.f if MCParticle has zero momentum at the penultimate trajectory point"
   "MCP_EndpointCompletenessU", "std::vector<double>", "U-view completeness of the 5cm region that preceeds the MCParticle endpoint", "-1.f if MCParticle has zero momentum at the penultimate trajectory point"
   "MCP_EndpointCompletenessV", "std::vector<double>", "V-view completeness of the 5cm region that preceeds the MCParticle endpoint", "-1.f if MCParticle has zero momentum at the penultimate trajectory point"
   "MCP_EndpointCompletenessW", "std::vector<double>", "W-view completeness of the 5cm region that preceeds the MCParticle endpoint", "-1.f if MCParticle has zero momentum at the penultimate trajectory point"               
   "MCP_EndpointPurity", "std::vector<double>", "purity of the 5cm region that preceeds the MCParticle endpoint", "-1.f if MCParticle has zero momentum at the penultimate trajectory point"
   "MCP_EndpointPurityU", "std::vector<double>", "U-view purity of the 5cm region that preceeds the MCParticle endpoint", "-1.f if MCParticle has zero momentum at the penultimate trajectory point"
   "MCP_EndpointPurityV", "std::vector<double>", "V-view purity of the 5cm region that preceeds the MCParticle endpoint", "-1.f if MCParticle has zero momentum at the penultimate trajectory point"
   "MCP_EndpointPurityW", "std::vector<double>", "W-view purity of the 5cm region that preceeds the MCParticle endpoint", "-1.f if MCParticle has zero momentum at the penultimate trajectory point"
   "MCP_HasMichel", "std::vector<int>", "whether the MCParticle has a true michel (grand)child at its endpoint", ""
   "MCP_MichelFromMuon", "std::vector<int>", "whether the parent is a muon or pion ", ""
   "MCP_HasTargetMichel", "std::vector<int>", "whether the MCParticle has a visible michel (grand)child at its endpoint", ""
   "BM_IsMichelRecod", "std::vector<int>", "does the michel MCParticle have a matched PFO?", ""   
   "MCP_MichelIndex", "std::vector<int>", "the index of the (grand)child michel in the PFO vectors", ""
   "BM_MichelIsChild", "std::vector<int>", "whether the parent-child link was reconstructed correctly", ""
   "BM_MichelIsShower", "std::vector<int>", "whether the reconstructed michel was classified as a shower", ""
   ..
