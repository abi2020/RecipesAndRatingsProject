# Recipes And Ratings Project
Project 3 for DSC 80<br>
By Abishek Siva
## Introduction

Analyzing a dataset of online recipes, encompassing details such as the number of ingredients, cooking time, nutritional information, and user ratings, holds importance for several reasons. Firstly, such an analysis can show patterns and trends in culinary preferences, providing valuable insights into popular ingredients, cooking techniques, and dietary preferences among users. This information can be used by food platforms and culinary enthusiasts to tailor content, creating recipes that resonate with a wider audience. Additionally, understanding the relationship between nutritional information and user ratings can inform healthier recipe development. 

Moreover, insights gained from the dataset can contribute to the optimization of user experience on recipe platforms, helping users discover and create dishes aligned with their preferences and dietary goals. Overall, the analysis of this dataset can enhance the quality and relevance of online culinary content, fostering a more engaging and satisfying experience for users seeking inspiration in the kitchen.

INTERACTIONS DATASET <br>
Number of Rows: 731927 <br>
Relevant Columns: `recipe_id` and `rating` <br>
Description: `recipe_id` allows us to merge both dataframes. The `rating` will be used to guage how much users liked or disliked a certain recipe.

RECIPES DATASET<br>
Number of Rows: 83782<br>
Relevant Columns: `id`, `minutes`, `n_steps`, `n_ingredients` <br>
Description: `id` allows us to merge both dataframes. The `minutes`, `n_steps`, and `n_ingredients` columns will be used to determine how complex a recipe is and how this might play into the rating given to a certain recipe.

## Cleaning

After merging these two dataframes, we start off by only looking at the columns that we are interested in analyzing. I also set the index to be the recipe id to make the future analysis easier.

## EDA

Univariate Analysis:<br>
The following graph shows the distribution of the number of minutes each recipe takes. Any value over 720 was changed to 720.

<iframe src="assets/dist_minutes.html" width=800 height=600 frameBorder=0></iframe>

The following graph shows the distribution of the number of steps in each recipe.

<iframe src="assets/dist_steps.html" width=800 height=600 frameBorder=0></iframe>






