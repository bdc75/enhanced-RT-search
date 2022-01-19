# enhanced-RT-search

I wrote this program to create a more refined movie search engine for [Rotten Tomatoes](https://www.rottentomatoes.com/browse/dvd-streaming-all).

## Why?

As is, their search engine limits the search criteria to the Tomatometer score range, availability on selected streaming platforms, and by genre(s). Their search criteria also includes an option to filter movies by their status of Certified Fresh... but this feature does not even work!

A movie has so many more meaningful attributes that may matter to a RT site user who wants a more refined search. Perhaps the user doesn't want to spend money on a movie, or only wants to see movies that are Certified Fresh, or movies that aren't longer than 2 hours, or movies released between the years 1970 and 2000, or... you get the point.

## Initial Observation

Despite their movie search engine lacking some important search criteria, RT provides a good deal of information about movies on the individual movie sites. See this for example:  [It's Such a Beautiful Day](https://www.rottentomatoes.com/m/its_such_a_beautiful_day). Displayed on this movie's page are all of the things we might care about when searching for movies that are not included in the RT search criteria:  Release Date, Runtime, Audience Score, and the Original Language.

## General Strategy

The program takes user input for the search criteria that RT does provide, loads the corresponding search result page, and to leverage the data provided on individual movie url's, it then filters movies by scraping data off of each movie's page.

*This process takes a lot less time than you'd imagine, since we can display search results by list (loaded through React and clicked on using Selenium), which displays a movie preview that include essential data used to eliminate them immediately, like Tomatoscore.*

## In summary:

In addition to taking user input for Tomatometer score range and desired genres, the program prompts the user for input on, and filters movies by, these added criteria:

- Original language
- Release date
- Runtime (movie length)
- Available for free or with subscription on a selected platform


#### *MORE DETAIL ON PACKAGES AND STRATEGIES USED:*

The amount of movies displayed on the initial search results URL is only 32. Because the "Show More" button at the bottom is activated through React, I made use of ***Selenium***, which is a WebDriver that is used to automate tasks like clicking buttons. I use Selenium to click the list-view button and click the "Show More" button a few times.

Viewing results in list-view format, as opposed to grid-view, allows me to see more data on the search results page and therefore limit the search pool much faster than by loading and scraping every single movie URL.



