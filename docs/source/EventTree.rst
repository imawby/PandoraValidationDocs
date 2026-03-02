EventTree
=====

.. _eventtree:

Source code can be found here: https://github.com/imawby/LArContent/blob/feature/Metrics/larpandoracontent/LArMetrics/EventValidationTool.cc
Plotting script can be found here: https://github.com/imawby/PandoraMetrics/blob/main/EventValidation.ipynb

Branches had several pre-fixes:

- MCEvent = variables that belong to the event e.g. particle multiplicity)
- MCInt = variables that describe the interaction e.g. its type)
- MCNu = variables that belong to the true neutrino interaction)
- RecoNu = variables that belong to the reco neutrino interaction)

  
.. csv-table::
   :header: "Branch Name", "Type", "Description"
   :widths: 15, 10, 30

   "Run", "int", "Run number"
   "Subrun", "int", "Subrun number"
   "Event", "int", "Event number"
   "EventCount", "int", "IGNORE"
   "MCEvent_NTargets", "int", "Number of MCParticles in the event that have more at least 5 hits in at least 1 views, and at least 15 hits overall"
   "MCNu_PDG", "int", "Nu PDG" 
   "MCNu_Energy", "float", "True nu energy [GeV]"
   "MCNu_VisEnergy", "float", "Nu interaction energy deposited in the detector (calc from EDepSims) [GeV]"
   "MCInt_IsCC", "int", "CC or NC interaction?"
   "MCNu_VertexX", "float", "x-coordinate of the first trajectory point that lies within the detector [cm]"
   "MCNu_VertexY", "float", "y-coordinate of the first trajectory point that lies within the detector [cm]"
   "MCNu_VertexZ", "float", "z-coordinate of the first trajectory point that lies within the detector [cm]"
   "RecoNu_VertexX_Pass1", "float", "x-coordinate of the reco nu vertex from pass 1 of the DLVertexingAlgorithm [cm]"
   "RecoNu_VertexY_Pass1", "float", "y-coordinate of the reco nu vertex from pass 1 of the DLVertexingAlgorithm [cm]"
   "RecoNu_VertexZ_Pass1", "float", "z-coordinate of the reco nu vertex from pass 1 of the DLVertexingAlgorithm [cm]"
   "RecoNu_VertexAcc_Pass1", "float", "(pass 1)reco-true nu vertex separation - +ve(-ve) values indicate a downstream(upstream) vertex [cm]"
   "RecoNu_VertexX", "float", "x-coordinate of the reco nu vertex from pass 2 of the DLVertexingAlgorithm [cm]"
   "RecoNu_VertexY", "float", "y-coordinate of the reco nu vertex from pass 2 of the DLVertexingAlgorithm [cm]"
   "RecoNu_VertexZ", "float", "z-coordinate of the reco nu vertex from pass 2 of the DLVertexingAlgorithm [cm]"
   "RecoNu_VertexAcc_Pass2", "float", "(pass 2)reco-true nu vertex separation - +ve(-ve) values indicate a downstream(upstream) vertex [cm]"
   ..

