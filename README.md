# <u>Political Bias in BERT</u>

<i>This repository contains all the scripts, datasets, and notebooks used for my study on finding Political Bias in pre-trained BERT models like BERT. </i>

## Overview
Transformers can learn universal language representations. They learn useful patterns and information from the dataset. Pre-trained models such as BERT and GPT-2 are trained on large quantities of unsupervised data. However, they can sometimes pick up undesirable and nuanced knowledge from the dataset they are trained on. For example, if the dataset that the model is trained on has a negative sentiment towards a particular entity, the model can learn that and inherit this negative sentiment. This gives rise to bias in these pre-trained models which can be in the form of gender or toward particular political entities. If not tackled early on, this bias could cause serious problems when these models are deployed in the real world. As Natural Language Processing (NLP) techniques become more and more popular in the world, it is more important to address this kind of social & political bias. 

In this project, I studied distilBERT, a pre-trained language model, and examined if there exists any inherent political bias. The main aim of this study is to check if BERT is biased toward a particular political entity such as Democrats or Republicans. After fine-tuning BERT on a set of political news articles, I tested the predictions of that model on a set of validation sentences that contain groups of covid-related topics. Moreover, I compute the sentiment of the MASK word being predicted by the model, to check if the model is more positively or negatively inclined towards different political entities - Democrats or Republicans.  

## Loading the dataset
Before running any of the models, you will need to load the training dataset in your Google Colab workspace. Once that is done, you can go ahead with model training.

## Model training
- To train the left leaning model run the `LLeaningPoliticalBiasInBERT.ipynb` notebook. 
This model also loads the dataset from Google drive and will use that dataset to train the model. 

- To train the right leaning model run the `RLeaningPoliticalBiasInBERT.ipynb` notebook. 
This model also loads the dataset from Google drive and will use that dataset to train the model. 

- To train the model on an unbiased news dataset, run the `CLeaningPoliticalBiasInBERT.ipynb` notebook. 

## Creating validation dataset
After the model is trained, we need a set of covid related validation sentences to test the model. To create this dataset, we can run the `ValidationDataset.ipynb` notebook. This will create a `covid_grouped_validation.csv` file that contains the validation sentences. 

We will use these sentences to test our model.

## Testing the model
Once the trained models and validation dataset are ready, we can test the model by running the `PoliticalBiasCovidDataset.ipynb` notebook. This will generate a set of results that contain the predictions of the model for those set of validation sentences. 

## Results
The complete set of validation results (base model, left leaning model and right leaning model) are saved in the results folder in the `final_validation_results.xlsx` file.
