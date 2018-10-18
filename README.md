# Amazon Data Science Project
Data science analysis project on Amazon consumer reviews.

## Obtaining Data Sets
We used two data sets in this project obtained from open-source database sites:
1. A set on baby products obtained from http://jmcauley.ucsd.edu/data/amazon/ (161k)
2. A larger set on phone products from https://data.world/promptcloud/amazon-mobile-phone-reviews (400k+)

## Cleaning the Data Sets
This project is based off analyzing word trends in consumer reviews based off the star(1-5) review the consumer provided
We stripped the data of all categories except: *review text*, *review rating*, and *was review helpful*

### Baby Data set:
- We imported the downloaded json file into ipython via pandas
- We then used panda functions to clean the data and remove certain data categories
- Finally we split the review text into five categories(text associated with 1 star reviews, text assoiciated with 2 stars... etc.)
- We created a csv file containg only the review text from each separated category i.e. one csv file for review text for one star ratings, one csv file for two star rating review text etc.

**_The code is contained within each .ipynb file_**

The following commands were then run:

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




