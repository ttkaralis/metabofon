# **Introduction**

Metabolic rewiring has long been recognized as an essential step for tumour growth and progression. Despite this, metabolomics is lagging behind other omics technologies, and large-scale metabolomic studies are missing. To address this issue, we developed a machine learning framework that allows prediction of metabolomics from gene expression data. Two different model types were selected and trained for tissues and cell lines, and were validated in independent data sets. Our data reveal that as high as 70-80% of tested metabolites can be correctly inferred from gene expression data across both cancer tissues and cell lines. This pipeline offers a promising approach for tracking cancer metabolism by analysing novel and existing datasets where only gene expression data is available.


# **General information**
This project presents a machine learning framework that predicts metabolomics from gene expression data.
 
All the cell line and tissue pre-trained models along with the scripts can be downloaded from https://zenodo.org/ using the accession number _**10.5281/zenodo.18347966**_ .

## **Model training**

Initially, we tested different traditional machine learning models for their ability to predict metabolomics from gene expression data. We trained cell line and tissue specific models:

![image alt](https://github.com/ttkaralis/metabolite_prediction_from_gene_expression/blob/6ed5caa0b62d48571bd7b1fd2ef83ce6b727465c/image_1.jpg)

We also tested different deep learning architectures to predict metabolomics in tissues:

![image alt](https://github.com/ttkaralis/metabolite_prediction_from_gene_expression/blob/6ed5caa0b62d48571bd7b1fd2ef83ce6b727465c/image_4.jpg)


## **Model validation**

The best models were selected and validated with independent tissue and cell line gene expression and metabolomic data:

![image alt](https://github.com/ttkaralis/metabolite_prediction_from_gene_expression/blob/6ed5caa0b62d48571bd7b1fd2ef83ce6b727465c/image_2.jpg)

And subsequently we combined the best model from the traditional machine learning approach with the best deep learning model:

![image alt](https://github.com/ttkaralis/metabolite_prediction_from_gene_expression/blob/6ed5caa0b62d48571bd7b1fd2ef83ce6b727465c/image_5.jpg)

## **Pipeline**

Using the pre-trained models from this repository it is easy to predict metabolomics straight from gene expression (RNA-Seq or microarrays):

![image alt](https://github.com/ttkaralis/metabolite_prediction_from_gene_expression/blob/6ed5caa0b62d48571bd7b1fd2ef83ce6b727465c/image_3.jpg)

# **User guidance**

In the "Script_for_the_user" we describe a simple workflow for the prediction of metabolomics from RNA-Sequencing data. A few things to keep in mind:
- The RNA sequencing data must be in TPM format (csv file, sample names in rows, gene names in columns).
- The gene features must be named with the stable Ensembl ID format, e.g.
- The script is designed to use only human Ensemble IDs. If you want to use data derived from other organisms (i.e. mouse) you have to perform orthology mapping elsewhere.

# **How to cite us**

If you found these models useful and you used them please cite our paper:








