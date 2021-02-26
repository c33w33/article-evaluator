# Article Evaluator

### Description

This tool predicts the page views of an article based its title and content.
Built with a machine learning backend, the tool predicts the page views based on:
- topic group it is associated with
- word count
- character count
- part of speech counts (# of nouns/verbs/adjectives/pronouns)
- FK Score/ FK Grade Level:[A metric on assessing difficulty of text](https://github.com/cdimascio/py-readability-metrics)
- Sentiment

This Github repository is only a shell of the original project made during 2019-2020. All proprietary and confidential information has been removed and this just serves as a guide on building similar applications.

### Data

Article Data was scraped using [Scrapy](https://scrapy.org) and settings used are stored in magcrawl folder. Model was trained on 2016-2019 articles of the client's website.

### Model

Data Prep was first done to prepare the data for training. Code is located in `training_dataset.py` and `gaprep.py`
Gensim LDA was used to model the topics of the articles. Code is located in `topic_modeling.py`
Graphical representations to see result of topic modeling can be seen in `graph.py`
XGBoost was used to predict the page views. Code is located in `regression_model.py`

The application itself has a separate code for cleaning the application input located in `textprep.py`

### Deployment Through Web Application

Streamlit was used to deploy the app.

### Running the App


Check the `requirements.txt` file for installation specs. You can install packages needed for this repo through:

```console
foo@bar:~$ pip install -r requirements.txt
```

Afterwards, `cd` into the directory of `app.py` and run this on the terminal:  

```console
foo@bar:~$ streamlit run app.py
```
