HierarchyTree
=============

.. _hierarchytree:


Branches had several pre-fixes:

- MC = variables that belong to the target MCParticle
- BM = variables that belong to the best-matched PFO
  
.. csv-table::
   :header: "Branch Name", "Type", "Description", "Default/Special Values"
   :widths: 15, 10, 30, 10

   "MC_HierarchyTier", "std::vector<int>", "True hierarchy tier within the 'visible' hierarchy", "1 == primary"
   "MC_ParentIndex", "std::vector<int>", "Index - in PFP array - of the true 'visible' parent", "-1 == parent is nu"
   "BM_HierarchyTier", "std::vector<int>", "Reco hierarchy tier", "-1 == no reco"
   "BM_ParentIndex", "std::vector<int>", "Index - in PFP array - of the reco parent", "-1 == no reco & -1 == parent is nu & -1 == parent is not a 'best match' (sorry)"
   ..
