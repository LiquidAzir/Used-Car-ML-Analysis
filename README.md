# Used-Car-ML-Analysis
This ML analysis looked at the drivers of used car prices from this dataset on Kaggle: https://www.kaggle.com/datasets/austinreese/craigslist-carstrucks-data.

After doing some testing and model iterations on the original dataset, I concluded that I needed to greatly simplify the features given the size and complexity of the dataset. I started by dropping all the columns which I did not believe added much value to the model and when encoded, would add significantly to the number of features.

I proceeeded to do some basic data cleaning including removing the NaN values.

I attempted to plot the distribution of price and relationship with odometer but was getting uninterpretable results. I realized that it may be due to outliers in the data so I created a new filtered dataframe using +/- 1.5 * the dataset IQR. This seemed to help significantly and I was able to create the plots.

I first wanted to run a simpler regression model with just the numerical features (Odometer and Year). I fit this via linear regrssion and checked the sqmean squared error, root mean squared error and R^2. The results were not adequate so I decided to incorprate all the remaining categrocial features. I did this via a pipeline to first preprocess the data (imputer, standardscalar, one-hot encoder) and then perform linear regression. These results were better with an R^2 score of about 52%. While improved, this indicated that only about 52% of the variation in price was explained by the features I had selected.

Finally, I ran a correlation matrix and created a chart of the importance of various features. The chart was helpful in determining that odometer had by far the largest affect on price, followed by vehicle type and year.

My recommendation to used car dealers would be:

Focus on mileage: Prioritize acquiring vehicles with low mileage as this is the biggest driver to price.
Diversify Inventory: Maintain a diverse range of vehicles, including popular types like sedans and SUVs, and consider the growing market for electric and hybrid cars.
Transparent Pricing Strategy: Use data-driven approaches to set competitive prices based on factors like year, condition, and mileage.
Highlight Key Features: Emphasize features that add value, such as low mileage, recent model years, and desirable car types or fuel options.
Marketing Strategy: Tailor your marketing to highlight the strengths of your inventory, focusing on aspects most valued by consumers, like mileage, condition, and type.
