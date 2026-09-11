# **Introduction**

Metabolomics provides a direct functional readout of tumour physiology, but lags behind other omics in enabling disease monitoring and prognostication. This limitation stems from the scarcity of large-scale metabolomic datasets and the technical challenges of measuring chemically diverse metabolites with widely varying abundancies. To address this, we developed Metabofon, a machine learning framework that predicts metabolite levels from gene expression across multiple cancer types, and implemented it as a user-friendly web platform accessible at https://software.icr.ac.uk/app/metabofon. Using this approach, we reconstructed the metabolic landscape of human tumours in the context of distinct oncogenic alterations. Leveraging these predictions, we identified and experimentally validated de novo pyrimidine synthesis as a selective vulnerability in PIK3CA-mutant breast cancer. Overall, this work establishes a scalable framework for inferring metabolomic states from transcriptomic data, enabling metabolic profiling in samples lacking direct measurements and facilitating the discovery of actionable metabolic dependencies in cancer.


# **General information**
This project presents a machine learning framework that predicts metabolomics from gene expression data.
 
All the cell line and tissue pre-trained models along with the scripts can be downloaded from https://zenodo.org/ using the accession number _**18347966**_ .

## **Model training**

Initially, we tested different traditional machine learning models for their ability to predict metabolomics from gene expression data. We trained cell line and tissue specific models:

![image alt](https://github.com/ttkaralis/metabofon/blob/6ed5caa0b62d48571bd7b1fd2ef83ce6b727465c/image_1.jpg)

We also tested different deep learning architectures to predict metabolomics in tissues:

![image alt](https://github.com/ttkaralis/metabofon/blob/6ed5caa0b62d48571bd7b1fd2ef83ce6b727465c/image_4.jpg)


## **Model validation**

The best models were selected and validated with independent tissue and cell line gene expression and metabolomic data:

![image alt](https://github.com/ttkaralis/metabofon/blob/b10d2d28111dbf8fa2f002a0c7bac08368035c98/image_2.jpg)

And subsequently we combined the best model from the traditional machine learning approach with the best deep learning model:

![image alt](https://github.com/ttkaralis/metabofon/blob/6ed5caa0b62d48571bd7b1fd2ef83ce6b727465c/image_5.jpg)

## **Pipeline**

Using the pre-trained models from this repository it is easy to predict metabolomics straight from gene expression (RNA-Seq or microarrays):

![image alt](https://github.com/ttkaralis/metabofon/blob/6ed5caa0b62d48571bd7b1fd2ef83ce6b727465c/image_3.jpg)

# **User guidance**

In the "Script_for_the_user" we describe a simple workflow for the prediction of metabolomics from RNA-Sequencing data. A few things to keep in mind:
- The RNA sequencing data must be in the following format: ".csv" file, sample names in rows, gene names in columns.
- The RNA sequencing data must be TPM-normalized.
- The gene features must be named with the stable Ensembl ID format, e.g. ENSG00000121879
- The script is designed to use only human Ensemble IDs. If you want to use data derived from other organisms (i.e. mouse) you have to perform orthology mapping elsewhere.

# **How to cite us**

If you found these models useful and you used them please cite our paper:

Metabofon infers tumour metabolomes from transcriptomic signatures to map oncogenic vulnerabilities

Theodoros Karalis (1), Aurelien Tripp (1), Agustina Salis Torres (1), Manas Kohli (1), Rachel Alcraft (2), Dandan Zhang (3), George Poulogiannis (1)

(1) Signalling and Cancer Metabolism Laboratory, Division of Cell and Molecular Biology, The Institute of Cancer Research; 237 Fulham Road, London SW3 6JB, United Kingdom

(2) Research Software Engineering Group, The Institute of Cancer Research; 237 Fulham Road, London SW3 6JB, United Kingdom

(3) The Department of Bioengineering, Translation and Innovation Hub, Imperial College, London UK 











