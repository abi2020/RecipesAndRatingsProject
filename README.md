# Recipes And Ratings Project
Project 3 for DSC 80<br>
By Abishek Siva
## Introduction

Analyzing a dataset of online recipes, encompassing details such as the number of ingredients, cooking time, nutritional information, and user ratings, holds importance for several reasons. Firstly, such an analysis can show patterns and trends in culinary preferences, providing valuable insights into popular ingredients, cooking techniques, and dietary preferences among users. This information can be used by food platforms and culinary enthusiasts to tailor content, creating recipes that resonate with a wider audience. Additionally, understanding the relationship between nutritional information and user ratings can inform healthier recipe development. 

Moreover, insights gained from the dataset can contribute to the optimization of user experience on recipe platforms, helping users discover and create dishes aligned with their preferences and dietary goals. Overall, the analysis of this dataset can enhance the quality and relevance of online culinary content, fostering a more engaging and satisfying experience for users seeking inspiration in the kitchen.

### Interactions Dataset
Number of Rows: 731927 <br>
Relevant Columns: `recipe_id` and `rating` <br>
Description: `recipe_id` allows us to merge both dataframes. The `rating` will be used to guage how much users liked or disliked a certain recipe.

### Recipes Dataset
Number of Rows: 83782<br>
Relevant Columns: `id`, `minutes`, `n_steps`, `n_ingredients` <br>
Description: `id` allows us to merge both dataframes. The `minutes`, `n_steps`, and `n_ingredients` columns will be used to determine how complex a recipe is and how this might play into the rating given to a certain recipe.

## Cleaning

After merging these two dataframes, we start off by only looking at the columns that we are interested in analyzing. I also set the index to be the recipe id to make the future analysis easier.

## EDA

### Univariate Analysis
The following graph shows the distribution of the number of minutes each recipe takes. Any value over 720 was changed to 720. We can see that the most common length of time that a recipe takes is 30 minutes.

<iframe src="assets/dist_minutes.html" width=800 height=600 frameBorder=0></iframe>

The following graph shows the distribution of the number of steps in each recipe. We can see that this is a Guassian distribution, but skewed to the right.

<iframe src="assets/dist_steps.html" width=800 height=600 frameBorder=0></iframe>

The following graph shows the distribution of the number of ingredients in each recipe. We can see that this is a Guassian distribution, but skewed to the right.

<iframe src="assets/dist_ingredients.html" width=800 height=600 frameBorder=0></iframe>

The following scatter plot shows the relationship between the number of steps and the Average rating for that recipe. We can see that up to around 25 steps, most recipes are getting around 4.5 to 5 stars on average.

<iframe src="assets/scatter.html" width=800 height=600 frameBorder=0></iframe>

## Assessment of Missingness

### NMAR Analysis

We will consider the missingness of the `rating` column. One of the possible reasons that the `rating` is NMAR is if people enjoyed making the recipe. People tend to usually only leave negative reviews to tell other people about their displeasure.

If the `rating` is MAR, it could be because people thought the recipe was too complex (had too many steps), meaning they decided not to try the recipe at all. 

### Missingness Dependency	
We will focus on the relationship between the missingness of `rating` and the missingess of `n_steps`. 

Null Hypothesis: The distribution of `n_steps` when `rating` is missing is the same as the distribution of `n_steps` when `rating` is not missing.<br>
Alternate Hypothesis: The distribution of `n_steps` when `rating` is missing is different from the distribution of `n_steps` when `rating` is not missing.<br>
Observed Statistics: The absolute difference between the means of both distributions.

The following graph shows the empirical distribution of the absolute means.

<iframe src="assets/emp_num_steps.html" width=800 height=600 frameBorder=0></iframe>

We can see that the observed mean was way outside of the other means. I calculated a p-value of 0.0, which falls under the 0.05 significance threshold. Thus, we reject the null hypothesis. We can now predict that `rating` is MAR when considering `n_steps`.

We will also look at the relationship between the missingness of `rating` and the missingess of `n_ingredients`.





