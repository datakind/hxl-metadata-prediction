# HXL Metadata Prediction

A data standard on platforms such as the [Humanitarian Data Exchange (HDX)](https://data.humdata.org/) is the [Humanitarian Exchange Language (HXL)](https://hxlstandard.org/), a column level set of attributes and tags and attributes which improve data interoperability and discovery. These tags and attributes are typically set by hand by data owners, which being a manual process can result in poor dataset coverage. Improving coverage through ML and AI techniques is desirable for faster and more efficient use of data in responding to Humanitarian disasters.

Previous work has focussed on fine tuning LLMs to complete tags and attrubutes, starting with the study [Predicting Metadata on Humanitarian Datasets with GPT 3](https://medium.com/towards-data-science/predicting-metadata-for-humanitarian-datasets-using-gpt-3-b104be17716d). This provides accurate results for common HXL tags related to location and dates, but is constrained by the quality of training data in being able to predict tags and attributes that are less frequently used (see [HXL standard](https://hxlstandard.org/standard/1-1final/tagging/).

This repo provides analysis for improvement to the fine tuning technique as well as a comparison. 

## Contents:

1. [generate-test=train-data.ipynb](generate-test=train-data.ipynb) - Notebook for creating test and traning data used by other notebooks
2. [openai-hxl-prediction.ipynb](openai-hxl-prediction.ipynb) - Notebok showing how to fine-tune and OpenAI model (GPT-4o) as well as use a non-fine tuning approach to directly prompt GPT-4o 

## Setup

### OpenAI API key

You will need to create an [API key in OpenAI](https://help.openai.com/en/articles/4936850-where-do-i-find-my-openai-api-key)

### Running in Google Colab

This repo provides a button on each notebook to run in [Google Colab](https://colab.research.google.com/). If using this method, you will also need to:

1. Set `OPENAI_API_KEY` to your OpenAI key in Colab secrets (click the little key icon on the left)
2. Create a folder on google drive, and update file paths in the notebooks accordingly, noting that the Google drive mount cell creates the mount at `/content/drive`

### Running locally

1. Install [miniconda](https://docs.conda.io/en/latest/miniconda.html) by selecting the installer that fits your OS version. Once it is installed you may have to restart your terminal (closing your terminal and opening again)
2. In this directory, open terminal
3. `conda env create -f environment.yml`
4. `conda activate hxl-prediction` use this runtime to run this notebook 
5. Adjust file pathc in the setup pane of notebooks appropriate to your environment