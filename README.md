Addition to Original Barnaba Code:
==================================

This is modified version of Barnaba package to calculate RNA pseudotorsion angles eta, theta, eta', and theta'.

Please refer original github here: https://github.com/srnas/barnaba

Following files are modified to include calculation of RNA pseudotorsion angles:

```nucleic.py, functions.py, definitions.py, and commandline.py```

Definitions of RNA pseudotorsion angles:
=========================================

Please refer to this nice blog by Dr. Xiang-Jun Lu (x3DNA-DSSR software page) for definitions of pseudotorsions:

https://x3dna.org/highlights/pseudo-torsions-to-simplify-the-representation-of-dna-rna-backbone-conformation

Requirements
-------------
Barnaba requires:
   - Python 2.7.x or > 3.3
   - Numpy
   - Scipy
   - Mdtraj 1.9
   - future
     
Barnaba requires mdtraj (http://mdtraj.org/) for manipulating structures and trajectories. 
To perform cluster analysis, scikit-learn is required too.

Required packages can be installed using `pip`, e.g.:

    pip install mdtraj

Installation (if you want RNA pseudotorsions !!!)
--------------------------------------------------

  git clone https://github.com/mandar5335/barnaba_pseudotor

then move to the barnaba directory and run the command

    pip install -e .

Usage:
------------
RNA pseudotorsions can be calculated using the command line or in jupyter-notebook.

command line:
-------------

``barnaba TORSION --pseudo --pdb foo.pdb``

Jupyter Notebook:
-------------------
```
import barnaba as bb
from barnaba import definitions
angle, res =  bb.eta_theta_angles("foo.pdb")
definitions.pseudo_angles
```

This will calculate four pseudotorsions: ['eta', 'theta', 'eta_prime', 'theta_prime']

References
------------

[1] Bottaro, Sandro, Francesco Di Palma, and Giovanni Bussi.  
    "The role of nucleobase interactions in RNA structure and dynamics."  
    Nucleic acids research 42.21 (2014): 13306-13314.  

If you use Barnaba in your work,  please cite the following paper::

	@article{bottaro2019barnaba,
  		title={Barnaba: software for analysis of nucleic acid structures and trajectories},
  		author={Bottaro, Sandro and Bussi, Giovanni and Pinamonti, Giovanni and Rei{\ss}er, Sabine and Boomsma, Wouter and Lindorff-Larsen, Kresten},
  		journal={RNA},
  		volume={25},
  		number={2},
  		pages={219--231},
		year={2019},
  		publisher={Cold Spring Harbor Lab}
	}
