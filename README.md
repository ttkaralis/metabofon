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

```markdown
```

 def hello():
    print("Hello, world!")


