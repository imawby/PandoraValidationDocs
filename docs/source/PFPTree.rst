PFPTree
=============

.. _pfptree:

Source code can be found here: https://github.com/imawby/LArContent/blob/feature/Metrics/larpandoracontent/LArMetrics/PFPValidationTool.ccs
Plotting script can be found here: https://github.com/imawby/PandoraMetrics/blob/main/PFPValidation.ipynb

Branches had several pre-fixes:

- MCP = variables that belong to the target MCParticle
- BM = variables that belong to the best-matched PFO
- ALT = variables describing the PFO that, aside from the best match, has the most of the MCParticle hits i.e. which PFO has stolen this MCParticle's hits?
  
.. csv-table::
   :header: "Branch Name", "Type", "Description", "Default/Special Values"
   :widths: 15, 10, 30, 10

   "Run", "int", "Run number", ""
   "Subrun", "int", "Subrun number", ""
   "Event", "int", "Event number", ""
   "EventCount", "int", "IGNORE", ""       
   "MCP_TruePDG", "std::vector<int>", "PDG of MCParticle", "777 == michels"
   "MCP_TrueEnergy", "std::vector<float>", "MCParticle energy [GeV]", ""
   "MCP_TrueVisEnergy", "std::vector<float>", "MCParticle visible energy (sum of EDepSims) [GeV]", " always 0 for VD - sorry :("
   "MCP_TrueThetaXZ", "std::vector<float>", "angle of the X-Z projected true direction to the Z-axis [radians]", "-4.f if MCParticle has zero initial momentum"
   "MCP_TrueThetaYZ", "std::vector<float>", "angle of the true direction to the Y-axis [radians]", "-4.f if MCParticle has zero initial momentum"
   "BM_IsTrack", "std::vector<int>", "whether the PFO was classified as a track by Pandora", "-1 == no reco"
   "BM_IsShower", "std::vector<int>", "whether the PFO was classified as a shower by Pandora", "-1 == no reco"
   "BM_HasMatch", "std::vector<int>", "whether the MCParticle has at least one matched PFO", ""
   "MCP_NMCHitsU", "std::vector<int>", "number of U-view hits belonging to the MCParticle", ""
   "MCP_NMCHitsV", "std::vector<int>", "number of V-view hits belonging to the MCParticle", ""
   "MCP_NMCHitsW", "std::vector<int>", "number of W-view hits belonging to the MCParticle", ""
   "MCP_NMCHits2D", "std::vector<int>", "number of 2D hits belonging to the MCParticle", ""
   "BM_NPfoHitsU", "std::vector<int>", "number of U-view hits belonging to the PFO", ""
   "BM_NPfoHitsV", "std::vector<int>", "number of V-view hits belonging to the PFO", ""
   "BM_NPfoHitsW", "std::vector<int>", "number of W-view hits belonging to the PFO", ""
   "BM_NPfoHits2D", "std::vector<int>", "number of 2D hits belonging to the PFO", ""
   "BM_NPfoHits3D", "std::vector<int>", "number of 3D hits belonging to the PFO", ""
   "BM_Completeness", "std::vector<float>", "completeness of the PFO considering all 2D hits", "0.0 if no reco"
   "BM_CompletenessU", "std::vector<float>", "completeness of the PFO considering U-view hits", "0.0 if no reco"
   "BM_CompletenessV", "std::vector<float>", "completeness of the PFO considering V-view hits", "0.0 if no reco"
   "BM_CompletenessW", "std::vector<float>", "completeness of the PFO considering W-view hits", "0.0 if no reco"
   "BM_CompletenessADC", "std::vector<float>", "adc-weighted completeness of the PFO considering all 2D hits", "0.0 if no reco"
   "BM_CompletenessADCU", "std::vector<float>", "adc-weighted completeness of the PFO considering U-view hits", "0.0 if no reco"
   "BM_CompletenessADCV", "std::vector<float>", "adc-weighted completeness of the PFO considering V-view hits", "0.0 if no reco"
   "BM_CompletenessADCW", "std::vector<float>", "adc-weighted completeness of the PFO considering W-view hits", "0.0 if no reco"
   "BM_Purity", "std::vector<float>", "purity of the PFO considering all 2D hits", "0.0 if no reco"
   "BM_PurityU", "std::vector<float>", "purity of the PFO considering U-view hits", "0.0 if no reco"
   "BM_PurityV", "std::vector<float>", "purity of the PFO considering V-view hits", "0.0 if no reco"
   "BM_PurityW", "std::vector<float>", "purity of the PFO considering W-view hits", "0.0 if no reco"
   "BM_PurityADC", "std::vector<float>", "adc-weighted purity of the PFO considering all 2D hits", "0.0 if no reco"
   "BM_PurityADCU", "std::vector<float>", "adc-weighted purity of the PFO considering U-view hits", "0.0 if no reco"
   "BM_PurityADCV", "std::vector<float>", "adc-weighted purity of the PFO considering V-view hits", "0.0 if no reco"
   "BM_PurityADCW", "std::vector<float>", "adc-weighted purity of the PFO considering W-view hits", "0.0 if no reco"
   "ALT_Completeness", "std::vector<float>", "completeness of the thief particle wrt the target particle", "-1.f if no thief"
   "ALT_Purity", "std::vector<float>", "purity of the thief particle wrt the target particle", "-1.f if no thief"
   "ALT_PDG", "std::vector<int>", "PDG of the MCParticle the thief best matches", "-1 if no thief"
   "ALT_IsUpstreamHierarchy", "std::vector<int>", "is the MCParticle that the thief best matches, an ancestor of this MCParticle?", "-1 if no thief"
   "ALT_IsUpstreamHierarchy", "std::vector<int>", "is the MCParticle that the thief best matches, an ancestor of this MCParticle?", "-1 if no thief"
   "MCP_VertexX", "std::vector<float>", "x-coordinate of the first trajectory point that lies within the detector [cm]", ""
   "MCP_VertexY", "std::vector<float>", "y-coordinate of the first trajectory point that lies within the detector [cm]", ""
   "MCP_VertexZ", "std::vector<float>", "z-coordinate of the first trajectory point that lies within the detector [cm]", ""
   "MCP_EndX", "std::vector<float>", "x-coordinate of the last trajectory point that lies within the detector [cm]", ""
   "MCP_EndY", "std::vector<float>", "y-coordinate of the last trajectory point that lies within the detector [cm]", ""
   "MCP_EndZ", "std::vector<float>", "z-coordinate of the last trajectory point that lies within the detector [cm]", ""
   "MCP_DirX", "std::vector<float>", "x-component of the true direction at the MCParticle vertex", "-9999.f if MCParticle has zero initial momentum"
   "MCP_DirY", "std::vector<float>", "y-component of the true direction at the MCParticle vertex", "-9999.f if MCParticle has zero initial momentum"
   "MCP_DirZ", "std::vector<float>", "z-component of the true direction at the MCParticle vertex", "-9999.f if MCParticle has zero initial momentum"      
   "MCP_EndDirX", "std::vector<float>", "x-component of the true direction at the penultimate trajectory point", "-9999.f if MCParticle has zero momentum at the penultimate trajectory point"
   "MCP_EndDirY", "std::vector<float>", "y-component of the true direction at the penultimate trajectory point", "-9999.f if MCParticle has zero momentum at the penultimate trajectory point"
   "MCP_EndDirZ", "std::vector<float>", "z-component of the true direction at the penultimate trajectory point", "-9999.f if MCParticle has zero momentum at the penultimate trajectory point"
   "MCP_Length", "std::vector<float>", "separation between the true vertex and true endpoint [cm]", ""
   "MCP_Displacement", "std::vector<float>", "separation between the MCParticle and MCNu vertices [cm]", ""
   "BM_VertexX", "std::vector<float>", "x-coordinate of the PFO's vertex [cm]", "-9999.f if no reco"
   "BM_VertexY", "std::vector<float>", "y-coordinate of the PFO's vertex [cm]", "-9999.f if no reco"
   "BM_VertexZ", "std::vector<float>", "z-coordinate of the PFO's vertex [cm]", "-9999.f if no reco"
   "BM_VertexAcc", "std::vector<float>", "signed true-reco vertex separation (+ve = downstream, -ve = upstream) [cm]", "-9999.f if no reco"
   "BM_Length", "std::vector<float>", "length from sqrt(LArPfoHelper::GetThreeDLengthSquared)", "-1.f if no reco"   
   "BM_Displacement", "std::vector<float>", "separation between the reco particle-neutrino vertices [cm]", "-1.f if no reco"     
   ..
