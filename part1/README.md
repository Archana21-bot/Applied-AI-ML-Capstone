Part 1 – Getting and Cleaning Data and Exploring It ## Project Overview This project is the part of the Applied AI & ML Essentials Capstone Project. The goal is to get, clean, analyze and visualize a world used car dataset before building machine learning models in the next parts. ## Dataset Description The dataset used is the Car Price Dataset. It has information about cars like brand, model, year made, mileage, fuel type, transmission, accident history and selling price.
 Dataset Details
1.	Number of Records: 4009
2.	Number of Features: 12
3.	Target Variable: price
4.	Numeric Features:
4.1.1.	model_year
4.1.2.	milage
4.1.3.	price
5.	Categorical Features:
5.1.1.1.	brand
5.1.1.2.	model
5.1.1.3.	fuel_type
5.1.1.4.	engine
5.1.1.5.	transmission
5.1.1.6.	ext_col
5.1.1.7.	int_col
5.1.1.8.	accident
5.1.1.9.	clean_title
The dataset was chosen because it has both number and category attributes. This makes it good for cleaning data exploring it visualizing it and making regression models.

Data Cleaning
Cleaning the Data The following steps were done to clean the data:
•	Loaded the dataset using Pandas.
•	Checked data. Dataset dimensions.
•	Looked for missing values.
•	Removed duplicate records.
•	Changed price from object to number.
•	Changed milage from object to number.
•	Changed category columns into category datatype.
Compared memory usage before and after changing datatype. # Looking for Missing Values Missing values were found using:
•	df.isnull().sum()
•	Percentage of missing values 


The columns with missing values were:
•	fuel_type
•	accident
•	clean_title 
No column had than 20% missing values. So numeric columns were filled with the median.     

Finding Duplicate 
Records Duplicate records were found using: 
•	Python
•	df.duplicated().sum()  
Duplicate rows were removed using:
•	Python
•	df.drop_duplicates()
  After removing duplicates the missing value percentages were checked again. This ensured consistency.

Data Type Correction
The following datatype changes were made:
•	Changed price from object to numeric.
•	Changed milage from object to numeric.
•	Changed  repeated category columns to category.
Memory usage was measured before. After changing datatype. This showed memory efficiency. 

Descriptive Statistics 
Descriptive statistics like:
•	Mean
•	Standard Deviation
•	Minimum
•	Maximum
•	Quartiles were computed for all features using df.describe().

 Checking Skewness 
Skewness was calculated for every feature. The feature with the absolute skewness was identified and analyzed. Interpretation
•	Positive skew means a tail toward higher values. In this case the mean is pulled upward by values.
•	Negative skew means a tail toward lower values. Here the mean is pulled downward by values. Since skewed distributions are sensitive to observations the median was preferred for filling missing values. 
Finding Outliers (IQR Method) 
Outliers were found using the Interquartile Range (IQR) method for:
•	price
•	milage 
Outliers were identified but not removed. 
Reason Car prices and mileage naturally have values. These are for luxury cars and heavily used vehicles. Removing these observations could discard information. So the outliers will be. Evaluated during model development in Part 2. 

Visualizations 
The following visualizations were made: 
•	Line Plot Shows how car prices vary across the dataset.
•	Bar Chart Shows the selling price across different fuel types. This visualization helps compare how fuel type affects vehicle price.
•	Histogram Shows the distribution of the skewed numeric feature. The histogram indicates if the feature follows an skewed distribution. 
•	Scatter Plot A scatter plot between Mileage and Price was made. 
•	Interpretation A negative relationship is observed between mileage and selling price. Generally cars with mileage tend to have lower resale prices. 
•	Box Plot A box plot comparing Price across fuel types was made. 
•	Interpretation The median selling price varies across fuel types. Some fuel categories have a spread and more outliers than others. 
•	Correlation Analysis A Pearson correlation matrix was. Visualized using a heatmap. The pair of variables with the absolute correlation was identified. 
•	Interpretation Although correlated variables move together correlation does not mean causation
For example the relationship between model_year and price may be influenced by third variables like:
•	Brand reputation
•	Vehicle condition
•	Mileage
•	Engine specifications 
These factors can jointly influence selling price. 

Mean vs Median Comparison
 For the two skewed numeric columns both the mean and median were calculated. The median was chosen for filling missing values. This is because it provides a measure of central tendency for skewed data. After filling all remaining missing values in these columns were successfully removed. 
Spearman Rank Correlation Both Pearson and Spearman correlation matrices were computed. The absolute differences between the two correlation methods were calculated. This was done to identify relationships that may be monotonic but non-linear. This is because regression models assume relationships. Spearman correlation will serve as a measure for detecting monotonic relationships. 
Grouped Aggregation 
Grouped statistics (mean standard deviation and count) were computed using Fuel Type as the grouping feature. 
Interpretation
•	The fuel type with the average selling price was identified.
•	The fuel type with the standard deviation showed greater price variability.
•	Higher within-group variability suggests that fuel type alone is not enough to predict vehicle price.
•	The ratio between the highest and lowest group means indicates that fuel type provides predictive information
Files Made
•	cleaned_data.csv
•	line_plot.png
•	bar_chart.png
•	histogram.png
•	scatter_plot.png
•	box_plot.png
•	correlation_heatmap.png 
Libraries Used
•	pandas
•	numpy
•	matplotlib

Conclusion 
The dataset was successfully. Explored. Missing values, duplicate records, incorrect data types, skewness, outliers and correlations were analyzed. Multiple visualizations provided insights into the data distribution and feature relationships. The cleaned dataset has been saved as cleaned_data.csv. Is ready for regression modeling in Part 2. In conclusion this analysis provides a foundation, for the next stage of the project.
