# Project 1 - House Rental Price Prediction Analysis

To get started: Add a file named "config.py" into the main directory (the same folder as the two house_rental.ipynb files).  
In this folder, include your API key in the format of: pop_key = "Your API Key". Save this file.  
API can be found at: https://api-ninjas.com/api/city  
To get an API key: make an account on the above site, log in and click on "My Account". Then, underneath the "API Key" subheading, click "Show API Key".  
  
Note: We assume that Rental Price is measured in Indian Rupees - but the original author doesn't actually state anywhere the units used for it.  
  
  
# Clean-Up:
Start by importing necessary dependencies.  
Then read the .csv file downloaded from Kaggle into a DataFrame (https://www.kaggle.com/datasets/iamsouravbanerjee/house-rent-prediction-dataset).  
Print the DataFrame to view it and get an idea of what needs to be done in the clean-up parts.  
Drop any duplicates by using the .drop_duplicates attribute.  
Then we removed the column named "Floor" as it won't be used in our analysis part.  
Then we renamed some columns to be read more easily.  
We then printed the count of different area types to see how many entries we are working with and get an overview of sample sizes for groups.  
We did the same thing for the different cities and localities in the dataframe.  
Then we plotted a boxplot to visually show the possible outliers, as well as calculating the quartiles for the "Rental Price" column of the dataset.  
From there, we were able to determine the lower and upper bounds, and we mathematically calculated where outliers would lie.  
Then, we removed those outliers so they don't skew the results in the analysis part.  
Finally, we saved the cleaned data frame to a .csv file.  

  

# Analysis:
Start by importing necessary dependencies.  
Then read the .csv file saved in the previous part.  
We then started by analyzing the influence house size has on the rental price. We did this by plotting a scatter plot of "house size vs. rental price". We then perfomred statistical analysis by performing linear regression, finding out the line equation, and using linregress to calculate the r-value for this relationship. R-value was found to be 0.394.  
We then performed the same steps, but only looking at rentals measured via "Carpet Area", as we thought rentals measured using "Super Area" may be skewing the data, due to the inclusion of common areas in those measurements. 
R-value for this relationship was found to be 0.325.  
We then created a bar chart to see the effect of "Area Type" on Rental Price. In this step, we performed statistical analysis by using one-way ANOVA between the 3 different area types. The p-value was found to be very small, which meant that this relationship was significant and most likely wasn't due to chance.  
We then performed the same steps when we looked at the effect of "City" on the rental price. The p-value from the one-way ANOVA was found to also be very low, which meant that the relationship is significant and wasn't due to chance.  
We then performed the same steps when we looked at the effect of "Furnishing Status" on the rental price. The p-value from the one-way ANOVA was found to also be very low, which meant that the relationship is significant and likely wasn't due to chance.  
We then performed the same steps when we looked at the effect of "Point of Contact" on the rental price. The p-value from the one-way ANOVA was found to also be very low, which meant that the relationship is significant and likely wasn't due to chance.  
We then performed the same steps when we looked at the effect of "City" on the rental price. The p-value from the one-way ANOVA was found to also be very low, which meant that the relationship is significant and likely wasn't due to chance.  
We then performed the same steps when we looked at the effect of "Number of Bathrooms" on the rental price. The p-value from the one-way ANOVA was found to also be very low, which meant that the relationship is significant and not due to chance. We noticed that the rental price increased as the number of bathrooms increased.  
We then used a population API called API_Ninjas which can be accessed through this link: "https://api.api-ninjas.com, which we used to find the populations for the 6 cities we have our data frame to see if population has an effect on rental price.  
Then, we created a new column in our data frame called "Population".  
We then looped through the dataframe, and we populated the "Population" column with the values found from the API against their corresponding cities in the data frame.  
Then, we performed one-way ANOVA between the 6 different populations to see what effect they have on rental price. The p-value was found to be very small, which meant that populcation has an effect on rental price, and observed differences in rental price were likely not due to chance.  
Finally, we changed the format for 2 columns in the dataset so it can be read easier.  
