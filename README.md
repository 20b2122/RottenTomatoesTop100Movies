# Listing Top 100 movies from Rotten Tomatoes

## Table of contents
* [Summary]
* [Installation]
* [Setup]

## Summary
* Extracting HTML data from [Rotten Tomatoes (Top 100 movies)] webpage
* Downloading and saving the the webpage as HTML into your computer and knowing how to access them.
* Using Requests, Pandas and BeautifulSoup libraries
* Finding the location of datas in HTML using [BeautifulSoup]
* Using [Pandas] to arrange the datas in table form showing the ranks, ratings, movies and number of watchers.
* link of webpage: https://www.rottentomatoes.com/top/bestofrt/


## Installation
* Requests library `!pip install requests`

* Pandas library `!pip install pandas`


* BeautifulSoup Library `!pip install beautifulsoup4`


## Setup
* Accessing the data from your computer 

`html_file = 'C:/Users/DELL/Documents/Python/data/rottentomatoes/top100.html'`
###### this depends on where you store the downloaded webpage



* Saving the url in a variable `url = 'https://www.rottentomatoes.com/top/bestofrt/'`



* Importing the libraries 

`import requests`

`import pandas as pd`

`import bs4 as BeautifulSoup`

* Finding the [class table] from HTML using beautifulsoup `table = soup.find('table',{'class':'table'})` 

* Storing the wanted data as an array eg. `movie_list=[]`

* Finding the location of wanted data eg. `movies = table.findAll('a')`

* Using for loop to store wanted data into array eg. `for movie in movies:`

* Using append on the list, the size of the list increases by one. eg.
`movie_list.append(movie.contents[0][2:])`
###### here '[2:]' is added to remove the first 2 letters from the 'movie.contents[0]'


* Creating a dictionary so that datas collected can be presented into a table `data = {}`

* Name of columns (from left to right): 'rank', ratings', 'movies', 'no. of watchers' 
```
data = {'ranks':rank_list,
        'ratings':rating_list,
        'movies':movie_list,
        'no. of watchers':watcher_list}
```


* Lastly, changing the first column into 'rank' removing the index 0-99 `df.set_index('ranks', inplace=True)`