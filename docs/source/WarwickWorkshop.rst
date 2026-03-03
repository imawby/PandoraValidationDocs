Warwick Workshop: Files
=======================

.. _warwickworkshopfiles:

For each category, there are two files:

- Validation file - this contains the patrec-focused metrics
- CCNuSel file - the ``ccnuselection/ccnusel`` tree contains the analysis-focused metrics (ignore ``warwickPIDSel``)

Nominal HD LBL
--------------

- ``/exp/dune/data/users/imawby/warwickWorkshop/nom_HD_LBL/validation_nom_HD.root``
- ``/exp/dune/data/users/imawby/warwickWorkshop/nom_HD_LBL/ccnu_nom_HD.root``  

Notes:

- Analysis tree contains PID from pandizzle/pandrizzle and Ivysaurus. These PID have been retrained wrt the latest production.

Nominal VD LBL
--------------

- ``/exp/dune/data/users/imawby/warwickWorkshop/nom_VD_LBL/validation_nom_VD.root``
- ``/exp/dune/data/users/imawby/warwickWorkshop/nom_VD_LBL/ccnu_nom_VD.root``

Notes:

- PID uses HD LBL weight files

Nominal HD Atmospheric
----------------------

- ``/exp/dune/data/users/imawby/warwickWorkshop/nom_HD_atmo/validation_nom_atmo.root``
- ``/exp/dune/data/users/imawby/warwickWorkshop/nom_HD_atmo/ccnu_nom_atmo.root``
  
Notes:

- No oscillation weights, or flux weights for this file
- PID uses HD LBL weight files

New shower-growing HD LBL
-------------------------

- ``/exp/dune/data/users/imawby/warwickWorkshop/shower_HD_LBL/validation_shower_HD_LBL.root``
- ``/exp/dune/data/users/imawby/warwickWorkshop/shower_HD_LBL/ccnu_shower_HD_LBL.root``
  
Notes:

- PID uses HD LBL weight files.

'Old' hit config HD LBL
-------------------------

- ``/exp/dune/data/users/imawby/warwickWorkshop/hit_HD_LBL/validation_hit_HD_LBL.root``
- ``/exp/dune/data/users/imawby/warwickWorkshop/hit_HD_LBL/ccnu_hit_HD_LBL.root``
  
Notes:

- ``physics.producers.gaushit.MaxMultiHit: 10``
- ``physics.producers.gaushit.Chi2NDF: 2000``
- PID uses HD LBL weight files.
   ..
