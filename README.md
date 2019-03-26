Data repository for the publication: ***Data-driven discovery of photoactive quaternary oxides using first-principles machine learning***

## Background

The high-throughput workflow uses a mixture of machine learning, data-driven models and first-principles calculations. The overall aim is to filter through a search space of 1 million quaternary oxide compositions to identify those that fall within a stated stability window, have a bandgap in the range 1.0 - 2.5 eV, and are comprised of earth-abundant elements. 

## Contents

#### Notebooks

**[Steps 1 and 2: Machine learning](https://github.com/WMD-group/Solar_oxides_data/blob/master/Step1_and_step2_machine_learning.ipynb)**

- Train a Gradient Boosting Regressor (GBR) model to predict bandgap from composition
- Filter newly generated compositions using the GBR model

**[Step 3: Data-driven filters](https://github.com/WMD-group/Solar_oxides_data/blob/master/Step3_data_driven_filters.ipynb)**

- Rank compositions by sustainability 
- Assign structures
- Apply oxidation state probability filter

**[Steps 4 and 5: Thermodynamic stability and electronic properties](https://github.com/WMD-group/Solar_oxides_data/blob/master/Step4_and_step5_first_principles_calcs.ipynb)**

- Thermodynamic stability calculations with high-throughput Density Functional Theory (DFT)
- Bandgap calculation with hybrid DFT

#### Data

The required data can be downloaded separately [here](https://zenodo.org/record/2600285#.XJKBzs_7RBw)
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.2600285.svg)](https://doi.org/10.5281/zenodo.2600285)
and should be untarred directly into this directory, creating a sub-directory named `data`. For the first notebook, a database is also required from [the CMR](https://cmr.fysik.dtu.dk/mp_gllbsc/mp_gllbsc.html#mp-gllbsc).

### Dependencies

The notebooks make use of many Python packages:

- [pymongo](https://api.mongodb.com/python/current/)
- [pymatgen](http://pymatgen.org)
- [matminer](https://hackingmaterials.github.io/matminer/)
- [scikit-learn](https://scikit-learn.org/stable/)
- [smact](https://github.com/WMD-group/smact)
- [pandas](https://pandas.pydata.org/)
- [atomate](https://atomate.org/)
- [fireworks](https://materialsproject.github.io/fireworks/)

```pip install pymongo pymatgen matminer scikit-learn smact pandas atomate fireworks```

### Caveats

- Some notebooks connect to the Materials Project using their API. It is therefore possible that data downloaded fresh may not exactly match data used for the work in the original paper. 
- The GBR model is built from scratch. Due to the randomness deliberately introduced in the training process, the predicted bandgap values of the same composition will vary slightly each time a new model is built.
- Many different libraries are used and I am not an expert in all of them: some of the code is probably far from elegant! 
