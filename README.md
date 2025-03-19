# **Introduction**

Metabolic rewiring has long been recognized as an essential step for tumour growth and progression. Despite this, metabolomics is lagging behind other omics technologies, and large-scale metabolomic studies are missing. To address this issue, we developed a machine learning framework that allows prediction of metabolomics from gene expression data. Two different model types were selected and trained for tissues and cell lines, and were validated in independent data sets. Our data reveal that as high as 70-80% of tested metabolites can be correctly inferred from gene expression data across both cancer tissues and cell lines. This pipeline offers a promising approach for tracking cancer metabolism by analysing novel and existing datasets where only gene expression data is available.

# **General information**
This project describes a machine learning framework that predicts metabolomics from gene expression data.

The pre-trained models are available to download from the "models" file. The cell line and tissue models are stored in the respective files.

All the scripts utilized for this study are availble in the "python_scripts" file. This contains separately the scripts used for cell lines and tissues.

# **User guidance**

In the "Metabolite_prediction_example.ipynb" a simple workflow for the prediction of metabolomics from RNA-Sequencing is described.

## **How to use the pre-trained models**

This script provides a generic example of how the user can load our pretrained models to predict metabolite levels directly from RNA sequencing data.
- The RNA sequencing data must be in TPM format (csv file, sample names in rows, gene names in columns).
- The name of the predicted metabolites must be loaded by the provided file ("y_train_features.pkl" which can be found in the same files as the pre-trained models), as the saved model does not include output names.

## **How to get started**

The following is a very handy tutorial for users that might have very limited knowledge of python.

First lets install and import the modules that we will use:

```
!pip install joblib
!pip install pandas
!pip install numpy
!pip install pickle

import pandas as pd
import numpy as np
import joblib
import pickle
```

Next, lets load the pre-trained model. In this example we will use Elastic Net:

```
model = joblib.load('ElasticNet.pkl')
```

And let's get the model training and output feature names:

```
#Input features
model_features = model.feature_names_in_
print(model_features)

#Load y features
with open('y_train_features.pkl', 'rb') as f:
    y_train_features_loaded = pickle.load(f)

print(y_train_features_loaded)
```

Now we import the RNA-Seq data, which should be TPM normalized. Remember that sample names should be in rows and gene names in columns:

```
rna = pd.read_csv('rna_tpm.csv')
```

Optionally, you can perform log2 transformation of the data. The code below adds +1 before applying log2 to avoid the presence of "0" which have undefined log2:

```
rna = rna.apply(lambda x: np.log2(x + 1))
```

Next, filter the genes that are present in our model. In this case, the metabolism associated-genes. Genes that might not be found in our RNA-Seq data are found added with NaN values:

```
features_not_in_data = list(set(model_features) - set(rna.columns))
for feature in features_not_in_data:
  rna[feature] = np.nan

filtered_data = rna[model_features]
```

Now we predict our metabolomics:

```
predictions = model.predict(filtered_data)
predictions = pd.DataFrame(predictions, index = filtered_data.index, columns = y_train_features_loaded)
```

And finally we can save our results to a csv file:

```
predictions.to_csv('predictions.csv', index = True)
```


# **How to cite us**

If you found these models usefull and you used them please cite our paper:








