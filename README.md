# BDMT_project_2022

In the last couple of years, there has been an enormous rise in the prices of real estate. Mainly due to global issues, but this industry has been always market-sensitive leading to significant housing bubbles or crashes. However, this industry is also a great contributor to annual GDP and becoming a popular investment option as opposed to volatile stocks or bonds. 

Relating to this, house price prediction is particularly important for new investors or sellers when dealing with real estate. Our topic would be exactly this. The subject of interest would be a hypothetical real estate company in Seattle, WA, USA, and the motive would be profit maximization based on predicted house prices. More specifically, the predicted prices can help our company choose if it is worth investing in this county, and in what type of properties.

## Exploratory data analysis

### Acquire and describe the data:

Our data is retrieved from the website called Kaggle, which is a huge repository of community published data and code. Our dataset consists all kinds of informations related to the real-estate industry. We can have a more details description of the data:

* **Id** - unique ID for each home sold
* **Date** - Date of the home sale
* **Price** - Price of each home sold
* **Bedrooms** - Number of bedrooms
* **Bathrooms** - Number of bathrooms, where 0.5 accounts for a room with a toilet but no shower
* **Sqft_living** - Square footage of the apartments interior living space
* **Sqft_lot** - Square footage of the land space
* **Floors** - Number of floors
* **Waterfront** - A dummy variable for whether the apartment was overlooking the waterfront or not
* **View** - An inde from 0 to 4 of how good the view of the property was
* **Condition** -An index from 1 to 5 on the condition of the apartment
* **Grade** - An index from 1 to 13, where 1-3 falls short of building construction and desing, 7 has an average level of construction and design, and 11-13 have a high quality level of construction and design
* **Sqft_above** - The square footage of the interior housing space that is above ground level
* **Sqft_basement** - The square footage of the interior housing space that is below ground level
* **Yr_built** - The year the house was initially built
* **Yr_renovated** - The year of the house's last renovation
* **Zipcode** - What zipcode area the house is in
* **Lat** - Lattitude
* **Long** - Longitude
* **Sqft_living15** - The square footage of interior housing living space for the nearest 15 neighbors
* **Sqft_lot15** - The square footage of the land lots of the nearest 15 neighbors

For even better representation of the dataset, we used **house_data.info()** and **house_data.describe()** for more detailed insight of dataset itself and numerical values that could be interesting to even better parse and prepare the dataset.

TODO: IMAGES


After the inspection of the missing values, we found out that there is no missing values. We used function ¸**isnull().sum()** to have a better representation of the missing values for each column. We can see that there is no missing values:
TODO: IMAGE WITH MISSING VALUES 

WE also need to dive into the outliers that we can remove for the purpose of better final results. Because **price** is the column that is the attiribute important for our research, we can use **sns.boxplot(x=house_data[price])** to better understand the range of values.

TODO: BOXPLOT PRICE IMAGE.

We can see that the majority of values spread in the range from 0.1 to 1 milion. We can also notice some of the expensive real-estates that are really far from this range. They are called outliers since there is not a lot of data rows of that value and the actual final results are not affected alot by them. We can remove them to make our dataset a bit smaller and on the same time, not polluted with the unecessary data that don't bring the extra added value.

After the decision to remove the outliers from the dataset (we removed rows with price value more than 1.5 milion dollars), the dataset seems more balanced and with better distributed data.

// TODO boxplot with removed outliers

### Data visualisation

#### Corellations between attributes
// TODO correlation image

Based on the correlation image, we can see that **price**, **sqft_living**, **sqft_above** and **grade** are the most correlated attributes. We can also see a big correlation betweeen **sqft_living** and **sqft_living15**, **sqft_lot** and **sqft_lot15** which implicises that there is an impact of the neighbourhood. We can also notice a small correlcation between **renovation** and **price**, also small correlation between **condition** and **yr_built** (we can assume that older building are also renovated so that means that they are not necessary in bad condition).
Based on the correlation values we can also assume what kind of factors can increase the price of the real-estate. We can assume that investment in **grade**, **sqft**, **view**, **waterfront** and the number of rooms can increase the *price** of the real-estate.

### Visualisation of some attributes

// TODO images 

Based on the graphs we can see above, we can see that majority of important attributes we presented have a normal distribution.


### Graph of price related to sqrt_living

// TODO add graph (maybe with linear regression?)

Based on the graph we can see a trend of **price** related to the **sqrt_living**. we can assume that bigger the living space of the real-estate, more expensive it is. We can confirm that by adding the linear regression line. Line has a positive trend.

### Graph of price related to yr_built
// TODO add image

Based on the graph where we represented the relation between **price** and **yr_built**, we cannot see a clear connection between these two attributes. This was also noticable with the small correlation values. We can assume that the newer apartments are expensive but the old ones are not cheaper. There can be some sentimental or historic value attached to the building (and renovated) and because of that they are holding the price high. We cannot assume that older building are cheaper.

### Graph of price related to grade.

// TODO add image of price - grade

We can see a clear (positive) trend that **price** is related to **grade**. Based on the graph we can assume that **price** is higher if **grade** is higher.

### Graph of price related to view.

// TODO add image of price - view

Based on the graph we can see a trend of **view** related to **price**. It seems that better view increases the price of the real-estate, but the differences are not big.

### Graph of price related to waterfont.

// TODO add image of price - waterfont

We can see that real-estates with **waterfont** view are more likely (more frequently) more expensive that the real-estates with not waterfront view. Correlation factor between these two attributes is small so we can assume that other attributes have an actual impact on the price and that there is no real connection between these two attributes.


### Graph of number of rooms related to price.
// TODO add image of price - bedrooms
// TODO add image of price - bathrooms

Based on the graphs we can see a trend of having more rooms, increases the price. Correlation value of these attributes in moderate.


