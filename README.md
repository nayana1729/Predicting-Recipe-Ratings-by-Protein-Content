# Protein Content and Recipe Rating Analysis
By: Nayana Naineni

## Introduction
Protein content in food is something that has become incredibly trendy. Due to the fitness industry and influencers from the same pushing the narrative that high-protein foods will lead to more muscle growth and athletic performance, I wanted to explore the relationship between protein content and recipe rating. This question helps us better understand nutrition and its impact on consumer preferences. I will utilize two datasets, called ratings and recipes, from food.com, a popular recipe-sharing website containing detailed data from 2008 onwards. There are 731927 rows in the first dataset with 5 columns and 83782 rows in the second dataset with 12 columns. For this project, the relevant columns include:

Ratings:

'rating' - Rating given

Recipes:

'minutes' - Minutes taken to prepare recipe  
'nutrition - Nutrition information in the form [calories (#), total fat (PDV), sugar (PDV), sodium (PDV), protein (PDV), saturated fat (PDV), carbohydrates (PDV)]; PDV stands for “percentage of daily value”  
'description' - User-provided description

## Data Cleaning and Exploratory Data Analysis
To clean the dataset, I first merged the two datasets to make working with the data easier and then replaced the 0 values in ratings with np.nan. This is because if calculating with 0s, they will seem like lower ratings even though in reality they are missing values. This helps us differentiate between actual ratings vs missing values. Then, I added a column with average ratings to understand the mean rating for each recipe. After that, I split nutrition into its individual values since we will utilize protein and calories for this project. Then, I kept only the relevant columns from this dataset. I also realized that some protein values were extreme (ex. 4000 grams) and I wanted to keep a threshold for the amount so I removed all rows that had a protein content of greater than 500 grams. 

### Univariate Analysis
<iframe src="assets/protein_uni.html" width="100%" height="600px"></iframe>

From this histogram, we can observe that the protein content is positively skewed with a right-tail. This tells us that the majority of the recipes have a moderate to low amount of protein content.

### Bivariate Analysis
<iframe src="assets/protein_ratings_box_plot.html" width="100%" height="600px"></iframe>

From this box plot, we can observe that a higher protein content means a higher rating. We can also see that there are many outliers, particularly for ratings 4 and 5. 

### Pivot Table
<iframe src="assets/pivot_table.html" width="100%" height="500px"></iframe>

I wanted to explore protein content and rating further by creating a range for protein and observing the average rating for those ranges. Interestingly, these averages are incredibly different from the plot relationship as the highest rating occurs for the protein range 400-500, however, the second highest is for the protein range 0-10. This shows that there may be other factors at play.

## Assessment of Missingness

Hypothesis Testing
Framing a Prediction Problem
Baseline Model
Final Model
Fairness Analysis
