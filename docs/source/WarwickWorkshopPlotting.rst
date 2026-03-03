Warwick Workshop: Plotting Scripts
==================================

.. _warwickworkshopplotting:

There is a separate set of plotting scripts for the patrec-focused (``validation*`` file) and the (``ccnusel`` tree) analysis-focused metrics, which can be found in the following GitHub repos:

- patrec-focused: https://github.com/imawby/PandoraMetrics
- analysis-focused: https://github.com/imawby/PandoraAnaMetrics



Pat-rec Focused Metrics
-----------------------

The ``validation*`` file contains several trees, each containing variables that examine different areas e.g. the shower-reco:

- ``AlgTree``: (ignore this one)
- ``EventTree``: examines event-level reconstruction performance e.g. is event-reco correct? neutrino vertex accuracy?
- ``HierarchyTree``: examines hierarchy reconstruction performance e.g. parent-child identification performance
- ``PFPTree``: examines generic PFO reconstruction e.g. completeness, purity, vertex accuracy...  
- ``TrackTree``: examines track reconstruction e.g. endpoint completeness, michel reconstruction
- ``ShowerTree``: examines shower reconstruction e.g. initial region purity, moliere radius

Each tree has a corresponding plotting script, which is found in the ``PandoraMetrics`` repo. This repo contains:

- ``EventValidation.ipynb``: Steering script to create the event-level metrics plots
- ``HierarchyValidation.ipynb``: Steering script to create the hierarchy-focused metrics plots
- ``PFPValidation.ipynb``: Steering script to create the generic pfo-focused metrics plots
- ``ShowerValidation.ipynb``: Steering script to create the shower-focused metrics plots  
- ``TrackValidation.ipynb``: Steering script to create the track-focused metrics plots  
- ``EventValidationFunc.py``: Contains the event-level metric plotting functions
- ``HierarchyValidationFunc.py``: Contains the plotting functions for the hierarchy-focused metrics
- ``PFPValidationFunc.py``: Contains the plotting functions for the generic pfo-focused metrics
- ``ShowerValidationFunc.py``: Contains the plotting functions for the shower-focused metrics
- ``TrackValidationFunc.py``: Contains the plotting functions for the track-focused metrics
- ``ValidationFunc.py``: Contains generic plotting functions
- ``Definitions.py``: Contains global variables, including the classification dictionaries and the corresponding mask creation functions e.g. interaction type, PDG type
- ``Variables.py``: Contains the plotting variable definitions

(If Isobel had time) Each plotting script exists as an interactive python notebook (.ipynb) and standard python script (.py). The plotting scripts mostly contain steering parameters and (in most cases) all functionality is contained in the ``*Func.py`` file. The scripts should run off the bat (if Isobel had time, they checked this). In each file you'll need to set ``file_name`` equal to the ``validation*`` file path and set ``plot_dir`` equal to where you want the output plots to live. The plotting scripts each create their own directory within a central ``Plots`` directory. 


Analysis-rec Focused Metrics
-----------------------

The analysis trees contain many variables that you can explore at your leisure, I have recreated my PhD CC nue/numu selection for you (lucky you!) in the ``PandoraAnaValidation`` repo, which contains:

- ``Analysis.ipynb`` - Contains the main CC numu/nue selection. Here I've implemented the CVN, Pandizzle/Pandrizzle and Ivysaurus selection. I've added in the HD energy correction factors (you may have to dig around dunereco for the VD energy correction factors) so that we have a semi-accurate reco energy.
- ``BDTVars.ipynb`` - Creates plots of the variables used in the Pandizzle/Pandrizzle selection (they're also an input to Ivysaurus).
- ``Definitions.py`` - Global variable definitions
- ``PlotPIDPerformance.ipynb`` - Plots the classification distributions, ROC curve and confusion matrices for the various PID methods.
- ``Plots.py`` - Contains the generic plot making functions
- ``Selection.py`` - Contains the functions that detail the CVN, Pandizzle/Pandrizzle and Ivysaurus selections
- ``Signal.py`` - Contains the functions that define the CC nue/numu signal
- ``TuneDoubleVarSelection.ipynb`` - Used to find the optimal cuts for a selection which relies on two cuts (i.e. the CC nue selection)
- ``TuneSingleVarSelection.ipynb`` - Used to find the optimal cuts for a selection which relies on one cut (i.e. the CC numu selection)

Running
-------

When it comes to running this code you have two options:

1. ``scp`` the input file(s) to your (or other) jupyter-tastic machine, pull the analysis repos and run the python scripts
2. use the dunegpvms

If you've chosen option 1. The only thing I will mention is to create and set the PLOT_DIR environment variable equal to the directory that you wish to put the plots i.e.:

``export PLOT_DIR=/exp/dune/app/users/imawby/PandoraMetrics``

If you've chosen option 2. then you'll need to follow these steps:

1. Pull the plotting repo
2. setup ``dunesw`` (or a random local larsoft build)
3. Inside your local version of the repo, create a virtual python environment:
   python -m venv /path/to/pulled/repo
   source bin/activate
   pip install uproot
   pip install matplotlib
   pip install scipy
4. export PLOT_DIR=/exp/dune/app/users/imawby/PandoraMetrics
5. run the python scripts
   
I think that's everything... Ah! I have noticed that the scripts take longer to run on the gpvms than on my laptop :( ``PFPValidation.py`` takes about 10mins to run...
   ..
