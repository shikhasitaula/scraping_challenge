# Overview
In this challenge we have performed various to qureries for web scraing. This challenge consists of two technical products. I have performed different logic to web scrap to the fowllowing deliverables:
1. **Scrape titles and preview text from Mars news articles.**
2.  **Scrape and analyze Mars weather data, which exists in a table.**
   
      The very first step taken for this challenge was importing the dependencies like splinter and beautiful Soup to move forward with the analysis. I have used automated browsing to visit the [Mars Temperature Data Site](https://static.bc-edx.com/data/web/mars_news/index.html)  and inspected the page to identify which elements to scrape.


#### 1. Scrape titles and preview text from Mars news articles:
   Here I assigned the browser as crome and provided the url to run in the browser. Next, Createed a Beautiful Soup object and use it to extract text elements from the website.Then ,extracted all the text elements by specifying **div** and the **class_=list_text'** where all the texts were stored, looped throuh each of the elements in the list and printed them. After that, I created an empty list to store the dictionaries, looped through the text elements to extract the tiltles and preview, stored each title and preview pair in a dictionary and finally the dictionary to the list using '.append' function.  **titles_list.append(article_teaser_body_dict)**

#### 2: Scrape and Analyze Mars Weather Data:
In this part of the analysis, I used beautiful Soup to check all the rows in the table "Mars temperature data". I used `rows = table.find_all('tr', class_='data-row')` to check for the rows and stored in the variable called rows and printed 5 of them to see how it looks. Next, I looped through all the rows then looped through all the items in each row and added those items list by using appending function.`data_row.append(row[i].text)`
`list_data.append(data_row)`. Further, we created the dataframe out of those data and named each columns. Then,  I changed the data type to help me for the analysis. I used the following logic to change the data type.
- mars_temperature_df[['min_temp', 'pressure']] = mars_temperature_df[['min_temp', 'pressure']].astype(str).astype(float)  
- mars_temperature_df['terrestrial_date'] = pd.to_datetime(mars_temperature_df['terrestrial_date'])
- mars_temperature_df[['sol', 'ls' , 'month']] = mars_temperature_df[['sol', 'ls', 'month']].astype(str).astype(int)
Next we used to groupby to group the temprature by minimum and calculated the average. `month_temperature =mars_temperature_df.groupby('month')['min_temp']`. Then plotted all the our filtered. Finally we tried to analyze the terrestrial date in the martian month. And tried to show the relation between the terrestrial_date and the minimum temperature.

We can conclude that nn average, the third month has the coldest minimum temperature on Mars, and the eighth month is the warmest. But it is always very cold there in human terms!Atmospheric pressure is, on average, lowest in the sixth month and highest in the ninth.The distance from peak to peak is roughly 1425-750, or 675 days. A year on Mars appears to be about 675 days from the plot. Internet search confirms that a Mars year is equivalent to 687 earth days.