# Windows-Laptops-Analysis

My objective was to analyze and visualize laptops based on their different functionalities, price, and rating. I utilized this [dataset](https://www.kaggle.com/datasets/kanchana1990/best-buy-2024-windows-laptops?resource=download), comprised of 489 entries of Windows laptops from Best Buy in 2024. 

### Tools and Libraries Used
* Pandas
* Matplotlib
* Plotly
* Seaborn

### Column Descriptions

* brand (489 non-null, object): The manufacturer of the laptop, covering a diverse range of well-known companies such as Dell, Lenovo, Microsoft, and more, indicating the dataset's breadth in representing different manufacturers.
* model (488 non-null, object): The specific model identifier for each laptop, providing a unique distinction between different laptop offerings.
* aggregateRating/ratingValue (357 non-null, float64): The average consumer rating for each laptop on a scale, reflecting overall consumer satisfaction.
* aggregateRating/reviewCount (357 non-null, float64): The total number of reviews submitted for each laptop, offering insight into the level of consumer engagement and feedback.
* offers/price (262 non-null, float64): The listed selling price for each laptop on Best Buy, crucial for price trend analysis and market positioning.
* offers/priceCurrency (489 non-null, object): The currency of the listed price, uniformly denoted as 'USD', ensuring consistency in price data.
* depth (431 non-null, float64): The front-to-back measurement of each laptop, contributing to the understanding of laptop size and portability.
* width (431 non-null, float64): The side-to-side measurement, further detailing the physical dimensions of the laptops.
* features/0/description (486 non-null, object): A description of a primary feature or selling point for the laptop, highlighting unique or standout specifications.
* features/1/description (483 non-null, object): Descriptions of a secondary feature, providing additional insights into the laptops' capabilities and attractions.

## Data Cleaning and Exploration

AFter renaming the columns and dropping those that I didn't intend to use, I filtered out any rows that did not contain values for the "Price" column. 

Next, I created a bar chart visualizing the Price per Brand. 

![pricevbrand](Images/pricevsbrand.PNG) 

Razer laptops are the most expensive laptop brand by average price by far. This would make sense because this brand is comprised of high performance gaming laptops.

I wanted to visualize laptops based on their ratings next so I dropped rows that did not have any ratings. I also created a new column in the dataframe called "Satisfaction Score" by dividing the "Rating" by the "Review Count". 

![cleaneddf](Images/cleaneddf.PNG) 

From there I created a scatter plot of Price vs Rating. 

![scatter](Images/scatter.PNG)

You can see a few laptops where rating is low and the price is high, vice versa, etc. However, this graph is difficult to interpret at a glace.

Next I explored the Satisfaction Score of each brand. 

![violin](Images/violin.PNG)

The violin plot illustrates that there is a roughly even distribution of customer satisfaction across brands except for GIGABYTE and Samsung laptops. These two brands have satisfaction scores of less than 2.

![histo](Images/histo.PNG)

After normalizing the satisfaction score using the "probabilty density" option of the histonorm value, Lenovo, Dell, Acer, and HP have the highest customer satisfication ratings. Next I will explore the brand counts.

![pie](Images/pie.PNG)

Taking a look at the laptop histogram and pie chart we can see the Lenovo, Dell, HP, Acer, and Microsoft are the top 5 brands with the most number of laptops within this cleaned dataset.

