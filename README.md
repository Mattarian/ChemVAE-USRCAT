# ChemVAE-USRCAT

## Getting the chemVAE library
To use the chemVAE download the VAE python library from:
https://github.com/aspuru-guzik-group/chemical_vae

The above link includes all the relevent instructions for training the VAE on new data, as well as the data from the work of R. Gómez-Bombarelli et al. There is also provided there a Jupyter Notebook (intro to chemVAE) which contains the necessary coding snippets to allow for the manipulation of the VAE after it has been trained. An adapted version of the notebook is provided in this repository, with some slight modifications to allow for greater user access.

## Models
Each of the models listed in this repository have been trained on a number of molecules with their respective USRCAT scores equivalent to the same reference molecule.
The SMILES of this molecule is provided here in a simple text file (cf. Reference_Mol.txt).

The primary model of interest in relation to current research is the one labelled as USRCAT_Sim_250K_with_ChemBL, provided here: 
https://github.com/Mattarian/ChemVAE-USRCAT/tree/main/USRCAT_Sim_250K_with_ChemBL

There are other models provided in this repository with slight variations from the above. In particular, the amount of data each model has been trained on differs, resulting in Machine Learning algorithms with different capabilities in molecular generation. These are detailed below.

- USRCAT_Sim_250K : A model trained on 250,000 molecules from ZINC with their USRCAT scores calculated relative to the reference molecule
- USRCAT_Sim_250K_with_Add_Mols : A model trained on 250,000 molecules from Zinc and a further 28 molecules from the work of C. Coxon et al.

## Using the Models
This has been trained on 250K drug-like molecules from ZINC, as well as 4K molecules from ChemBL which are known to have CDK-2 activity.
To load and use a specific model, create (or activate) an anaconda environment with the following requirements:
- Python >= 3.5
- Keras >= 2.0.0 && <= 2.0.7
- Tensorflow == 1.1
- RDKit
- Numpy

*It is possible the computer may throw an error when attempting to run, which may be caused by the Keras backend not being set correctly. The commands in the notebook file should correct this, but if not, locate the Keras file in the env lib area and forcibly set Keras_Backend = Tensorflow*

Then, in the conda environment, load the Jupyter Notebook. Following the instructions in the notebook, input a molecule to be used as the "seed". The seed molecule must be provided in SMILES format, however the choice SMILES format (ie. Isomeric, Cannonised etc.) is not particularly important for the running of the code. *That being said, if possible, use cannonised SMILES as it simplifies the running a bit as the code then does not have to cannonise the SMILES itself*

Run the seed a couple of times through the code to ensure it is not being mis-translated. As the VAE is probabalistic this may take a few attempts, and if it is not possible to translate the seed successfully, either select a new seed or go with the best-attempted translation as this may just be an output error.

# Refernces
R. Gómez-Bombarelli, J. Wei, D. Duvenaud, J. Hernández-Lobato, B. Sánchez-Lengeling, D. Sheberla, J. Aguilera-Iparraguirre, T. Hirzel, R. Adams and A. Aspuru-Guzik, ACS Cent. Sci., 2018, 4, 268-276.

C. Coxon, E. Anscombe, S. Harnor, M. Martin, B. Carbain, B. Golding, I. Hardcastle, L. Harlow, S. Korolchuk, C. Matheson, D. Newell, M. Noble, M. Sivaprakasam, S. Tudhope, D. Turner, L. Wang, S. Wedge, C. Wong, R. Griffin, J. Endicott and C. Cano, J. Med. Chem., 2017, 60, 1746-1767.
