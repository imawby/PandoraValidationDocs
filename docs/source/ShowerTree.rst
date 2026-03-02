ShowerTree
==========

.. _showertree:

Source code can be found here: https://github.com/imawby/LArContent/blob/feature/Metrics/larpandoracontent/LArMetrics/ShowerValidationTool.cc
Plotting script can be found here: https://github.com/imawby/PandoraMetrics/blob/main/ShowerValidation.ipynb

Branches had several pre-fixes:

- MCP = variables that belong to the target MCParticle
- BM = variables that belong to the best-matched PFO
  
.. csv-table::
   :header: "Branch Name", "Type", "Description", "Default/Special Values"
   :widths: 15, 10, 30, 10

   "Run", "int", "Run number", ""
   "Subrun", "int", "Subrun number", ""
   "Event", "int", "Event number", ""
   "MCP_TrueCoreLengthFromU", "std::vector<float>", "3D length that captures 90% of the charge in the U-view", "-1.f if initial momentum is zero"
   "MCP_TrueCoreLengthFromV", "std::vector<float>", "3D length that captures 90% of the charge in the V-view", "-1.f if initial momentum is zero"
   "MCP_TrueCoreLengthFromW", "std::vector<float>", "3D length that captures 90% of the charge in the W-view", "-1.f if initial momentum is zero"
   "BM_RecoVtxX", "std::vector<float>", "x-coordinate of the PFO vertex given under a shower hypothesis (logic matches PandoraShower)", "-1.f if no reco or if fit fails"
   "BM_RecoVtxY", "std::vector<float>", "y-coordinate of the PFO vertex given under a shower hypothesis (logic matches PandoraShower)", "-1.f if no reco or if fit fails"
   "BM_RecoVtxZ", "std::vector<float>", "z-coordinate of the PFO vertex given under a shower hypothesis (logic matches PandoraShower)", "-1.f if no reco or if fit fails"
   "BM_RecoDirX", "std::vector<float>", "x-component of the initial direction obtained by a PCA (logic matches PandoraShower)", "-1.f if no reco or if fit fails"
   "BM_RecoDirY", "std::vector<float>", "y-component of the initial direction obtained by a PCA (logic matches PandoraShower)", "-1.f if no reco or if fit fails"
   "BM_RecoDirZ", "std::vector<float>", "z-component of the initial direction obtained by a PCA (logic matches PandoraShower)", "-1.f if no reco or if fit fails"
   "BM_RecoCoreLength", "std::vector<float>", "3D length that captures 90% of the charge in the W-view", "-1.f if no reco or if fit fails"
   "BM_RecoLength", "std::vector<float>", "3D length given by the PCA", "-1.f if no reco or if fit fails"
   "BM_DirAcc", "std::vector<float>", "opening angle between true and reco initial directions [radians]", "-1.f if no reco or if fit fails"
   "BM_MoliereRadius", "std::vector<float>", "the transverse 3D distance (from the core shower axis) that captures 90% of the charge in the W-view", "-1.f if no reco or if fit fails"
   "MCP_InitialMCHits", "std::vector<int>", "number of 2D MCParticle hits in the 14cm following the MCParticle vertex", "-1.f if initial momentum is zero"
   "MCP_InitialMCHitsU", "std::vector<int>", "number of U-view MCParticle hits in the 14cm following the MCParticle vertex", "-1.f if initial momentum is zero"
   "MCP_InitialMCHitsV", "std::vector<int>", "number of V-view MCParticle hits in the 14cm following the MCParticle vertex", "-1.f if initial momentum is zero"
   "MCP_InitialMCHitsW", "std::vector<int>", "number of W-view MCParticle hits in the 14cm following the MCParticle vertex", "-1.f if initial momentum is zero"
   "BM_InitialPfoHits", "std::vector<int>", "number of 2D PFO hits in the 14cm following the MCParticle vertex", "-1.f if initial momentum is zero"
   "BM_InitialPfoHitsU", "std::vector<int>", "number of U-view PFO hits in the 14cm following the MCParticle vertex", "-1.f if initial momentum is zero"
   "BM_InitialPfoHitsV", "std::vector<int>", "number of V-view PFO hits in the 14cm following the MCParticle vertex", "-1.f if initial momentum is zero"
   "BM_InitialPfoHitsW", "std::vector<int>", "number of W-view PFO hits in the 14cm following the MCParticle vertex", "-1.f if initial momentum is zero"
   "BM_InitialCompleteness", "std::vector<float>", "completeness of the 14cm region that follows the MCParticle vertex", "-1.f if initial momentum is zero"
   "BM_InitialCompletenessU", "std::vector<float>", "U-view completeness of the 14cm region that follows the MCParticle vertex", "-1.f if initial momentum is zero"
   "BM_InitialCompletenessV", "std::vector<float>", "V-view completeness of the 14cm region that follows the MCParticle vertex", "-1.f if initial momentum is zero"
   "BM_InitialCompletenessW", "std::vector<float>", "W-view completeness of the 14cm region that follows the MCParticle vertex", "-1.f if initial momentum is zero"
   "BM_InitialPurity", "std::vector<float>", "purity of the 14cm region that follows the MCParticle vertex", "-1.f if initial momentum is zero"
   "BM_InitialPurityU", "std::vector<float>", "U-view purity of the 14cm region that follows the MCParticle vertex", "-1.f if initial momentum is zero"
   "BM_InitialPurityV", "std::vector<float>", "V-view purity of the 14cm region that follows the MCParticle vertex", "-1.f if initial momentum is zero"
   "BM_InitialPurityW", "std::vector<float>", "W-view purity of the 14cm region that follows the MCParticle vertex", "-1.f if initial momentum is zero"
   ..
