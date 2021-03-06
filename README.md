# Churn prediction for Music Streaming Service

This project analyzes event log data from a fictional music streaming service that is provided by Udacity. The goal was to analyze the data, find features that are correlated with user churn and build a machine learning model which allows to predict user churn. Knowing which users might churn allows Sparkify's team to target these users specifically, e.g. with a retention campaign with special offers. Have a look a the full documentation of the project in [this Medium post](https://medium.com/@quandtreas/thinking-about-cancelling-your-music-subscription-23dc4674a299).


## Content
The structure of this repo is very simple: the `notebooks` folder contains a notebook `Streaming Music.ipqnb`, which contains the complete analysis. A separate `data` folder exists, however the file is too large to be uploaded to github. In case the notebook is rerun, the data must be retrieved from [Udacity's server](https://video.udacity-data.com/topher/2018/December/5c1d6681_medium-sparkify-event-data/medium-sparkify-event-data.json).
    
## Installation
All required packages are listed in `requirements.txt`. If you are using `anaconda`/`miniconda` use following command to set up a new environment 
with all requirements to run the code:
```
conda create --name <name of the environment> --file requirements.txt
```

## Usage
Before rerunning the notebooks, the data needs to be downloaded from the link above and put into the `data` directory.

To run the notebook locally, make sure pyspark is installed on your machine. Steps for installation can be found online easily (I used [this](https://medium.com/swlh/pyspark-on-macos-installation-and-use-31f84ca61400) and [this](https://medium.com/macoclock/how-to-install-apache-pyspark-on-macbook-pro-4a9249f0d823) article).
Also make sure that the following commands in the notebook are not commented out:
```
import findspark
findspark.init()
```
Alternatively, the notebook can be run on a cloud platform, such as Databricks. Make sure that the platform includes `Spark 3.0`.

### Results
Due to the imbalance in the data set (far fewer users who churned than those who did not) the f1-score was chosen as an evaluation metric for both, model selection during grid search in the final model evalution. The f1-score is the harmonic mean of precision and recall [(Wikipedia)](https://en.wikipedia.org/wiki/F1_score).

The tested **Logistic Regression** model achieved the following result

```
f1-score: 0.29
Recall: 0.2
Precision: 0.5
```

An overview over the analysis and the results can be found in **[this blog post](https://medium.com/@quandtreas/thinking-about-cancelling-your-music-subscription-23dc4674a299)**

## Contributing
PRs accepted, feel free to contribute.

## License
MIT © A. Q.
