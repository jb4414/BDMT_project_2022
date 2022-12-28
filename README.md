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

