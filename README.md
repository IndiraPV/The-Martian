# The Web Scaping Challenge
## Mission to Mars

## live [demo]()

![mission_to_mars](Images/mission_to_mars.png)

For this challenge developed a web application that scrapes various websites for data related to the Mission to Mars and 
displays the information in a single HTML page. 

### Step 1 - Scraping

Scraping was done in Jupyter Notebook using BeautifulSoup, Pandas, Selenium and Splinter libraries.

### NASA Mars News

* Scraped the [NASA Mars News Site](https://mars.nasa.gov/news/) and collected the latest News Title and Paragraph Text. 

```python
# Example:
news_title = "NASA's Next Mars Mission to Investigate Interior of Red Planet"

news_p = "Preparation of NASA's next spacecraft to Mars, InSight, has ramped up this summer, on course for launch next May from Vandenberg Air Force Base in central California -- the first interplanetary launch in history from America's West Coast."
```

### JPL Mars Space Images - Featured Image

* JPL Featured Space Image [link](https://www.jpl.nasa.gov/spaceimages/?search=&category=Mars).

* Used Selenium/Splinter to navigate the site and find the image url for the current Featured Mars Image and assign the url string to a variable called `featured_image_url`.

* The image url was the full size `.jpg` image.

* Complete url string for this image was saved.

```python
# Example:
featured_image_url = 'https://www.jpl.nasa.gov/spaceimages/images/largesize/PIA16225_hires.jpg'
```

![featured_image](Images/featured_image.PNG)

### Mars Weather

* Visited the Mars Weather twitter account [here](https://twitter.com/marswxreport?lang=en) and scraped the latest Mars weather tweet from the page. Saved the tweet text for the weather report as a variable called `mars_weather`.

```python
# Example:
mars_weather = 'Sol 1801 (Aug 30, 2017), Sunny, high -21C/-5F, low -80C/-112F, pressure at 8.82 hPa, daylight 06:09-17:55'
```

### Mars Facts

* Visited the Mars Facts webpage [here](https://space-facts.com/mars/) and used Pandas to scrape the table containing facts about the planet including Diameter, Mass, etc.

* Used Pandas to convert the data to a HTML table string.


### Mars Hemispheres

* Visited the USGS Astrogeology site [here](https://astrogeology.usgs.gov/search/results?q=hemisphere+enhanced&k1=target&v1=Mars) to obtain high resolution images for each of Mar's hemispheres.

* Each links to the hemispheres was clicked in order to find the image url to the full resolution image.

* Both the image url string for the full resolution hemisphere image, and the Hemisphere title containing the hemisphere name was saved in a Python dictionary using the keys `img_url` and `title`.

* Appended the dictionary with the image url string and the hemisphere title to a list. This list will contain one dictionary for each hemisphere.

```python
# Example:
hemisphere_image_urls = [
    {"title": "Valles Marineris Hemisphere", "img_url": "..."},
    {"title": "Cerberus Hemisphere", "img_url": "..."},
    {"title": "Schiaparelli Hemisphere", "img_url": "..."},
    {"title": "Syrtis Major Hemisphere", "img_url": "..."},
]
```
![final_app_part2](Images/final_app_part2.png)

## Step 2 - MongoDB and Flask Application

The scraped data was imported in as Python dictionaries and persisted in MongoDB. With Flask templating created a new HTML page that displays all of the information that was scraped from the URLs above.Used Bootstrap4 to structure HTML template.


### Copyright

Indira V. Poovambur © 2019.
