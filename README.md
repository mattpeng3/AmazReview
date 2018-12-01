# **Creators: Matt Peng, Scott Xue, Conrad Chan, Grace Zhang, Alan Huh**

# Amazon Data Science Project
Data science analysis project on Amazon consumer reviews.

## About the Code and Files
**Data_sets_used:** This folder contains the zip files for the data sets used - a file on Amazon baby products, another on Amazon phone products.

**Analysis:** This contains two excel datasheets with all the review text organized corresponding to each review star ordered by the words that occur the most first.

**Scripts:** This folder contains all the code and scripts. If a file has graphs in its name, this ipython notebook file then showcases graphs of trends within teh review text in Amazon reviews.


## Obtaining Data Sets
We used two data sets in this project obtained from open-source database sites:
1. A set on 5-core baby products obtained from http://jmcauley.ucsd.edu/data/amazon/ (161k)
2. A larger set on phone products from https://data.world/promptcloud/amazon-mobile-phone-reviews (400k+)

## Cleaning the Data Sets
This project is based off analyzing word trends in consumer reviews based off the star(1-5) review the consumer provided
We stripped the data of all categories except: *review text*, *review rating*, and *was review helpful*

### Data set:
- We imported the downloaded json/csv file into ipython via pandas
- We then used panda functions to clean the data and remove certain data categories
- Finally we split the review text into five categories(text associated with 1 star reviews, text assoiciated with 2 stars... etc.)
- We created a csv file containg only the review text from each separated category (i.e. one csv file for review text for one star ratings, one csv file for two star rating review text etc).

**_The code is contained within each .ipynb file_**

The following commands were then run on each created csv file, however we converted these bash scripts to Python:

```
tr -c -s '[:alpha:]' '[\n*]' < File_Name | \

sort | \

uniq -c | \

sort -n -r -k 1,1 | \

sed #q
```

**File_Name**
>Place the file name/location here [/User/name/Desktop/file.csv]

**#**
>Place the number of words wanting to parse, meaning if # = 20, this gets the top 20 most commonly used words

# Analysis/Algorithm:
Within the **scripts folder** our algorithm is written utilizing jupyter notebook and python. Essentially what we did was:
1. Strip the datasets and organize the reviews based off which category they belong to i.e. one star, two star review...
2. Clean up and delete symbols, numbers, and common words
3. Create five arrays, one for each rating, containing the most popular, approximately top 200 words, that were used from the reviews under that rating category
4. The algorithm then traverses through a review assigning each word a score based off which rating array they are found in and the ouput is a score 1-5, along with which words had the most positive score and which words were the most negative ones used


If you would like to contribute, contact me:
mattpeng3@gmail.com
---------------------------------------------



