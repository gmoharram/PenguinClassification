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

Additionally, the penguin feature distributions can be looked at depending on the penguin sex.

<p align="center">
  <img src="https://github.com/gmoharram/PenguinClassification/blob/main/img/PairplotSex.png" />
</p>

Now, if we combine these two labels - species and sex - we get the following distribution.

<p align="center">
  <img src="https://github.com/gmoharram/PenguinClassification/blob/main/img/PairplotSpeciesSex.png" />
</p>

# Classification

The sklearn decision tree module is used for classification.

Two options present themselves if we would like to be able to idetify both the species and the sex of a penguin based on its size measurements.
Either to predict the newly created combined label 'Species_Sex', or train two seperate decision trees on the 'Species' and 'Sex' label and combine the results retroactively.
In the <a href='https://github.com/gmoharram/PenguinClassification/blob/main/PenguinClassification.ipynb'>jupyter notebook</a> the results of both those approaches are shown.

At a depth of 6, the species decision tree presents a testing accuracy of 97.6%.
Here the standard sklearn parameter values are used - the gini index as the impurity measure and a 'best' split approach which tries out all possible feature splits.

<p align="center">
  <img src="https://github.com/gmoharram/PenguinClassification/blob/main/img/speciesTree.png" />
</p>

Furthermore, at a depth of of 10, the sex decision tree has a testing accuracy of 90.5%. 
In this case an entropy split criterion had better performance.

<p align="center">
  <img src="https://github.com/gmoharram/PenguinClassification/blob/main/img/sexTree.png" />
</p>

In total, this two step approach brings out total species-sex test prediction accuracy to 88.33%, assuming a perfect overlap between the correctly predicted test points.

On the other hand, the simultaneous prediction of the combined 'Speciec_Sex' label had test set accuracy of 89.3%. 
This decision tree had a depth of 13. The entropy criterion was used in addition to a 'random' splitter.

<p align="center">
  <img src="https://github.com/gmoharram/PenguinClassification/blob/main/img/speciesAndSexTree.png" />
</p>




