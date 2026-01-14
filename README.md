# Capstone-Project-24.1-Final-Report (README)
This is the final Capstone project and includes the following items:
Capstone Final Report (PDF) - contains more details and charts (follows the template provided)
Capstone Final Jupyter notebook - contains all the code and comments plus a number of additional plots and charts 
README exec (high-level) template provided 
Extra work Jupyter notebook (supplemental) - some informal work to see how a neaural network would perform on the dataset 

Capstone Project Overview

Red Wine Rating System 
1.	Define the Problem Statement: 
The goal of this project is to use machine learning to be able to accurately predict the quality rating a red wine would receive from a human judge based on its physical and chemical characteristics.  Initially, I had also hoped to translate that into estimating how a wine would place in a wine competition, but quickly realized that was going to be too big of a problem to tackle for this assignment.  So, for this project I will just focus on building a model that will accurately predict the quality rating, which will serve as a guide to a wine drinker to know if the wine will be good to drink.

In other words, I want my model to answer the questions:  How would a human judge rate the quality of this wine?  Based on that rating, will this wine taste good?

2.	Model Outcomes or Predictions: 
As stated in my capstone EDA report, the problem could be approached two ways from a machine learning perspective.  One could take a Linear Regression approach and train models to produce a numerical score and map that score to the closest human judge rating (0-10).   Alternatively, another approach could be to view the human rating (0-10) as each being separate class and train classification models to produce the predicted rating.

After discussion with my advisor (Savio), it was clear that the classification model would be preferred as it is more definitive in terms of which rating class (0-10) the wine falls into.  Also, the metric of accuracy  in the classifier model is easier to interpret than MSE in the linear regression model.

3.	Data Acquisition: The deliverable at this step is to identify what data you plan to acquire and use with your model. For the best results, data should come from multiple sources and your analysis for including specific data should be clear. Please provide a clear visualization to assess the data’s potential to solve the problem as well.
For this step I needed to find a dataset that I could work use within the scope of what I could accomplish based on the techniques learned at that point in the class.  Many of the wine judging competitions do not publish a lot of detailed data on the wines selected and what is published is often based on vague descriptors such as taste profiles like “cherry” or “baking spice” or “spicy” or “structured”, and so that sound like fancy wine terms and are purely subjective.  To try and build a model that could vectorize all of those terms was clearly beyond the scope of this effort.  (That will be something for future exploration.)

I found a dataset and discussed it with Savio, who agreed it was a good fit in the UCI machine learning repository 
(https://archive.ics.uci.edu/dataset/186/wine+quality) 

The UCI dataset contains red Vinho Verde wines from Northern Portugal.  Each of the wines is defined by 11 physical/chemical characteristics and then given a score between 0 and 10 by wine judges.  0 is terrible and 10 is outstanding wine.  In the actual dataset all of the wines judged fall  in the range of 3 to 8. 

 
In my research, there were very few datasets that could even come close to this in terms of the number of quantitative features of the wine and the resulting target value of a human rating (score).  The majority of datasets only quantify residual sugars and alcohol content.  Those simple features, while very influential, do not provide enough information to separate high quality from low quality wines. 

4.	Data Preprocessing/Preparation: 
Preparing the data was more straightforward than some of the datasets I have worked with throughout the course.  As noted in the accompanying Jupyter notebook, I ran through the steps to ensure there was no missing data or null values.  I also checked for duplicate data and initially it appeared that there were some (240 samples of 1599), however after researching it and finding that each of those samples represents an independent observation (wine sample being judged) it would be best to keep them, otherwise information would be lost.

The data was all numerical so there was no need initially for techniques like “one-hot encoding” or “ordinal encoding”.  I also applied standard scaling where appropriate and did not with certain classifiers like decision trees, as noted in the Jupyter notebook.  Additionally, thinking ahead I did want to better understand the linearity of the relationship between key variables and the target (‘quality’).  I used a number of scatter plots as shown in the Jupyter notebook to conclude the relationship was pretty linear, and that polynomial transformation would not be beneficial to the model performance.  (I had actually confirmed that during the EDA report where I played with polynomial degree 2 and did not get a better result.) 

Later, after running initial models, it became clear that I would need to do some further feature engineering to further improve the results, as clearly documented in the accompanying Capstone Jupyter notebook.  After some thought and exploring how some of the wine experts (such as those published in Wine Spectator Magazine) categorize wines, I decided to re-map the ratings in the dataset to something that would be useful, going back to the original goal, to a wine drinker of discriminating taste in selecting a good wine to drink.  As documented in the Jupyter notebook, I mapped the ratings of 3 to 8 in the dataset as follows: 

7-8: “very good”
5-6: “good”
3-4: “not good”

I explained in more detail why I chose those ratings and it was directly from a well respected source that many wine drinkers rely upon for selecting a good wine.  This re-mapping of the data so that instead of there being 6 classes, there were now just three resulted in an improvement of the accuracy from mid-60% to mid-80% range— pretty substantial improvement.

5.	Modeling: Please see the Capstone Report (PDF) and the Capstone Jupyter notebook for more deatils on models chosen.  In summary multiple classification models and related ensemble methods:
   Logistic Regression
  	K-Near Neighbors
  	Decision Tree
  	SVC
  	Random Forest (ensemble)
  	Bagging (ensemble)
  	Stacking (ensemble)


7.	Model Evaluation: Charts with the best results for each of the models and ensemble above are contained in the Capstone Final Report and can also be found in the Capstone Jupyter notebook.  There are two sets of results.  The fisrt set is the results before doing some further feature engineering to reduce the classes from 6 to 3 in the dataset.  The rationale for this is explained in the report and the Jupyter notebook comments, as well as above in section 4.

Best score for each type of model (rounded to one decimal place)
Model
               Cross-validation Score	    Test Score 
Random Forest 	86.6%	                     86.9%
SVC 	          85.1%	                     86.3%
KNeighbors 	   84.1%	                     84.7%
Stacking 	     85.9%	                     85.9%

















 

