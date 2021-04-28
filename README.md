# ChemVAE-USRCAT

To use the chemVAE download the VAE library from:
https://github.com/aspuru-guzik-group/chemical_vae

The above will include all the relevent instructions for training the VAE on new data. There is also provided there a Jupyter Notebook with the necessary data to allow
for the manipulation of the VAE after it has been trained.

Each of the models listed in this repository have been trained on a number of molecules with their respective USRCAT scores equivalent to the same reference molecule.
The SMILES of this molecule is provided here in a simple text file.

The primary model of interest in relation to current research is the one provided here: 
https://github.com/Mattarian/ChemVAE-USRCAT/tree/main/USRCAT_Sim_250K_with_ChemBL

This has been trained on 250K drug-like molecules from ZINC, as well as 4K molecules from ChemBL which are known to have CDK-2 activity.
