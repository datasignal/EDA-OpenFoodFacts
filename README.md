# EDA - Open Food Facts

This repository is deep exploratory data analisys of the Open Food Facts dataset. It is a very long notebook with lots of code, explanation and insights.

The dataset is relatively huge with about 360'000 observations and 160 variables and a size of about 1 Go. For this reason, it is not provided in this repository but can be downloaded at this URL: https://www.kaggle.com/openfoodfacts/world-food-facts

The following packages are required to execute the notebook :
* `python`
* `numpy`
* `pandas`
* `matplotlib`
* `seaborn`
* `scipy`
* `beautifulsoup4`

If using `conda`, a ready to use environment can be created with the commands :
```bash
# Create the conda environment
> conda create -f environment.yml

# Activate the environment
> conda activate eda-openfoodfacts

# Launch Jupyter notebook server
> jupyter notebook
```

Here is the notebook outline :

## A. Importing and Cleaning the data

The goal of this part is to get a very high level understanding of the data :

1. Importing the data from a tsv file
2. Basic and safe cleaning
3. Data summary and variables identification 
4. Missing values analysis

## B. Manipulating the data

This part dives deeper in the data and is splitted in three different analysis tasks and goals :

### B.1 Domain and Data Source Knowledge  

Everytime we ask the data, we get an answer. Without no knowledge about the origin of the data, how they have been collected, where do they come from, the answers could be biased and we would have no way of guessing it. 

In this first topic, we will work with the `creator`, `created_datetime` and `states_tags` to answer these questions and get very valuable insights about the data and their quality. We will also see if the OpenFoodFact project is a living project. 

### B.2 Allergen Analysis

In this part, the goal will be to identify the most common allergens in food.

Because the data are really messy, it will be a real pain to get this answer, a lot of string manipulation and regular expression will be required. Last but not least, there are multiple langages in the data, so we will translate the allergens by building a translation dictionary by using web scrapping techniques.

### B.3 Food Macronutrients Composition and Energy

In this part, we will investigate the macronutrients breakdown across various kind of food. We will use the `pnns_groups 1 & 2` classification variables to summarize our results. We will look at if there are correlation between energy and the macronutrients breakdown (carbohydrates, fats and proteins).


## C. Text data and manipulation

In this part, the goal is to find the five most common ingredients and get an opportunity to manipulate text data with `pandas`

## D. Time-series analysis

In this section, we will investigate about the mean time difference between the `created_datetime` and the `last_modified_datetime` variables. We will also investigate about the mean number of created items per month over the timeline of the data.


## E. Build a database

In this part, we will create a SQLite database, import the data from our DataFrame into the database, respecting its schema and finally query the data from the database with SQL.

## F. Finding correlations

In this section, we try to identify the variables which most affect the nutritional score and find correlation between them. Stay tuned because the nutritional score is for sure, at least, a mysterious metric.
