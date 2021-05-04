# ChemVAE-USRCAT

To use the chemVAE download the VAE python library from:
https://github.com/aspuru-guzik-group/chemical_vae

The above link includes all the relevent instructions for training the VAE on new data. There is also provided there a Jupyter Notebook (intro to chemVAE) which contains the necessary coding snippets to allow for the manipulation of the VAE after it has been trained. An adapted version of the notebook is provided in this repository, with some slight modifications to allow for greater user access.

Each of the models listed in this repository have been trained on a number of molecules with their respective USRCAT scores equivalent to the same reference molecule.
The SMILES of this molecule is provided here in a simple text file (cf. Reference_Mol.txt).

The primary model of interest in relation to current research is the one labelled as USRCAT_Sim_250K_with_ChemBL, provided here: 
https://github.com/Mattarian/ChemVAE-USRCAT/tree/main/USRCAT_Sim_250K_with_ChemBL

This has been trained on 250K drug-like molecules from ZINC, as well as 4K molecules from ChemBL which are known to have CDK-2 activity.
To load and use a specific model, create (or activate) an anaconda environment with the following requirements:
- Python >= 3.5
- Keras >= 2.0.0 && <= 2.0.7
- Tensorflow == 1.1
- RDKit
- Numpy

*It is possible the computer may throw an error when attempting to run, which may be caused by the Keras backend not being set correctly. The commands in the notebook file should correct this, but if not, locate the Keras file in the env lib file and forcibly set Keras_Backend = Tensorflow*

Then, in the conda environment, load the Jupyter Notebook. Following the instructions in the notebook, input a molecule to be used as the "seed". The seed molecule must be provided in SMILES format, however the choice SMILES format (ie. Isomeric, Cannonised etc.) is not important particularly important for the running of the code. *That being said, if possible, use cannonised SMILES as it simplifies the running a bit as the code then does not have to cannonise the SMILES itself*
