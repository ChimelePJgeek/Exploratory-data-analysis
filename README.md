# Exploratory-data-analysis
EDA using Python
In this project I used a pairplot to visualize the relationship between different features in different species and also examined the body mass distribution within the classified species

#Data loading and preprocessing
import numpy as np
import pandas as pd
peng = pd.read_csv(r"C:\Users\Chimele\Desktop\datasets\penguins_size.csv")
peng
#description summary of data
peng.describe()
#Checking missing values
peng.isnull().sum()
#replacing missing values
process_column = ['culmen_length_mm', 'culmen_depth_mm', 'flipper_length_mm',
                  'body_mass_g', 'sex']
for item in process_column:
    peng[item].fillna(peng[item].mean(), inplace = True)
    print(peng.iloc())
    peng
peng.isnull().sum()
#data visualization
import matplotlib.pyplot as plt
import seaborn as sns
sns.pairplot(peng.drop(['island'], axis = 1),hue='species')
#body mass distribution
sns.boxplot(x=peng.species,y=peng.body_mass_g,palette='pastel')
plt.title("Body mass distribution",fontsize=18)

Data obtained from:
Gorman KB, Williams TD, Fraser WR (2014) Ecological Sexual Dimorphism and Environmental Variability within a Community of Antarctic Penguins (Genus Pygoscelis). PLoS ONE 9(3): e90081. doi:10.1371/journal.pone.0090081
