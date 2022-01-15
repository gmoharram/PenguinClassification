# PenguinClassification
Antarctica Penguin Species Classification

Data collected on antarctic penguin species is used to train a species classifier.
The data was provided by Dr. Kristen Gorman and the Palmer Station, Antarctica LTER.

Gorman KB, Williams TD, Fraser WR (2014) Ecological Sexual Dimorphism and Environmental Variability within a Community of Antarctic Penguins (Genus Pygoscelis). PLoS ONE 9(3): e90081. doi:10.1371/journal.pone.0090081


# Data Exploration

When inspecting the distributions of the penguin size features, it becomes clear that training a decision tree classifier on the data is likely to produce reliable species predictions.

<p align="center">
  <img src="https://github.com/gmoharram/PenguinClassification/blob/main/img/PairplotSpecies.png" />
</p>

Additionally, the penguins can further be divided by sex.

<p align="center">
  <img src="https://github.com/gmoharram/PenguinClassification/blob/main/img/PairplotSpeciesSex.png" />
</p>

# Classification

The sklearn decision tree classifier is used to predict the species, the sex and the species AND sex of the penguins.
