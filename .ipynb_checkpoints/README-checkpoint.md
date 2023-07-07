# Overview
In this challenge we have performed various to qureries for web scraing. This challenge consists of two technical products. I have performed different logic to web scrap to the fowllowing deliverables:
1. **Scrape titles and preview text from Mars news articles.**
2.  **Scrape and analyze Mars weather data, which exists in a table.**
   
      The very first step taken for this challenge was importing the dependencies like splinter and beautiful Soup to move forward with the analysis. I have used automated browsing to visit the [Mars Temperature Data Site](https://static.bc-edx.com/data/web/mars_news/index.html)  and inspected the page to identify which elements to scrape.


#### 1. Scrape titles and preview text from Mars news articles
   Here I assigned the browser as crome and provided the url to run in the browser. Next, Createed a Beautiful Soup object and use it to extract text elements from the website.Then ,extracted all the text elements by specifying **div** and the **class_=list_text'** where all the texts were stored, looped throuh each of the elements in the list and printed them. After that, I created an empty list to store the dictionaries, looped through the text elements to extract the tiltles and preview, stored each title and preview pair in a dictionary and finally the dictionary to the list using '.append' function.  **titles_list.append(article_teaser_body_dict)**