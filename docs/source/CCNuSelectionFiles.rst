CCNuSelection Trees
===================

.. _ccnuselection:

I don't have time to create a lovely table for you. I think that this tree is fairly self explanatory (although I have been staring at it for ~4 years). I think the only things I need to mention is that:

- Ignore the ``warwickPIDSel`` tree (I think it's only in the atmospheric files)
- The trees are filled such that each entry corresponds to an event, and each element in the arrays stored on the branches is a PFP (not MCParticle like in the metrics trees!!)
- The tree is filled assuming either a track or shower fit (depending on the Pandora classification) i.e. if a PFO is shower-like, only the RecoShower* variables are calculated, the RecoTrack* elements will equal default values.

If you get stuck, have a look at the CCNuSelection_module.cxx (in the GitHub repo I point to - the dunereco main branch one is messier).
   ..
