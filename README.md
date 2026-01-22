# **Introduction**

Metabolic rewiring has long been recognized as an essential step for tumour growth and progression. Despite this, metabolomics is lagging behind other omics technologies, and large-scale metabolomic studies are missing. To address this issue, we developed a machine learning framework that allows prediction of metabolomics from gene expression data. Two different model types were selected and trained for tissues and cell lines, and were validated in independent data sets. Our data reveal that as high as 70-80% of tested metabolites can be correctly inferred from gene expression data across both cancer tissues and cell lines. This pipeline offers a promising approach for tracking cancer metabolism by analysing novel and existing datasets where only gene expression data is available.


# **General information**
This project presents a machine learning framework that predicts metabolomics from gene expression data.

All the cell line and tissue pre-trained models along with the scripts can be downloaded from https://zenodo.org/.

## **Model training**

Initially, we tested different traditional machine learning models for their ability to predict metabolomics from gene expression data. We trained cell line and tissue specific models:

<img src="./image_1.jpg" width="400">

We also tested different deep learning architectures to predict metabolomics in tissues:

<img src="./image_4.jpg" width="400">


## **Model validation**

The best models were selected and validated with independent tissue and cell line gene expression and metabolomic data:

<img src="./image_2" width="400">

And subsequently we combined the best model from the traditional machine learning approach with the best deep learning model:

<img src="./image_5" width="400">

## **Pipeline**

Using the pre-trained models from this repository it is easy to predict metabolomics straight from gene expression (RNA-Seq or microarrays):

<img src="./image_3" width="400">

# **User guidance**

In the "Script_for_the_user" we describe a simple workflow for the prediction of metabolomics from RNA-Sequencing data.

## **How to use the pre-trained models**

This script provides a generic example of how the user can load our pretrained models to predict metabolite levels directly from RNA sequencing data. A few things to keep in mind:
- The RNA sequencing data must be in TPM format (csv file, sample names in rows, gene names in columns).
- The name of the predicted metabolites must be loaded by the provided file ("y_train_features.pkl" which can be found in the same files as the pre-trained models), as the saved model does not include output names.

# **How to cite us**

If you found these models useful and you used them please cite our paper:








