### Capstone 
Author: Curtis Phare 

#### Executive summary (please see the Capstone Final Report PDF for more detail)
The goal of this project is to use machine learning to be able to accurately predict the quality rating a red wine would receive from a human judge based on its physical and chemical characteristics using various machine learning models.

#### Rationale
This will enable a wine maker or a wine drinker to assess the quality of a wine based on its physical/chemical charateristics, before it is released or purchased in quantity.

#### Research Question
 Based on physical/chemical characteristics, I want my model to answer the questions:  How would a human judge rate the quality of this wine?  Based on that rating, will this wine taste good?


#### Data Sources
I found a dataset and discussed it with Savio, who agreed it was a good fit in the UCI machine learning repository 
(https://archive.ics.uci.edu/dataset/186/wine+quality) 

The UCI dataset contains red Vinho Verde wines from Northern Portugal.  Each of the wines is defined by 11 physical/chemical characteristics and then given a score between 0 and 10 by wine judges.  0 is terrible and 10 is outstanding wine.  In the actual dataset all of the wines judged fall  in the range of 3 to 8. 

#### Methodology
The question could be answered using  linear regression modeling methods or using a classification modeling methods.  I chose the latter because it is more definitive and the evaluation of the models effectiveness is easier to interpret.

#### Results
In the end, I found (as summarized in my capstone report) that Random Forest ensemble method could accurately predict the wine quality as being 'Not good', 'Good', or 'Very Good' with almost 87% accuracy.  See table of results in Capstone Final Report (PDF).


#### Next steps
As a next step I would like to further explore using a neural network with a softmax output layer.  Also, I would like to consider how to vectorize some additional datasets where the wine characteristics are expressed in verbal "wine tasting language" to see if it is possible to acheive a high judging score accuracy.

#### Outline of project

- https://github.com/curt-lab/Capstone-Project-24.1-Final-Report.git
- capstone_final.ipynb



##### Contact and Further Information
