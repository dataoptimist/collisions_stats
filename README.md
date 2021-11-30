## Navigation

This README.md will be the source of information for navigating through the repository.

* `analysis - EDA.ipynb`: jupyter notebook with exploratory data analysis & preprocessing of data
* `analysis - modeling.ipynb`: jupyter notebook with model training and results
* `images` folder: contains visualizations
* `feature_descriptions.docx`: document of feature descriptions
* `CollisionRecords.txt`: dataset of collisions characteristics from 2016 - 2020 in California
* `PartyRecords.txt`: dataset of party characteristics in collisions from 2016 - 2020 in California
* `VictimRecords.txt`: dataset of victim characteristics in collisions from 2016 - 2020 in California
* `presentation.pdf`: slide deck of project overview and findings

## Introduction: Business Opportunity

This project is designed to analyze collision data in California, from 2016 - 2020, exploring the factors that might contribute to collisions and the severity of such collisions. From there, possible business recommendations can be made to reduce the severity of collisions.


## Approach

Through various visualizations techniques, the goal will be to spot any patterns in collisions in the nature of their occurrence and identify any possible predictive factors that might lead to collisions.

From there, I'll use modeling techniques to develop a model that can predict the severity of a collision, given existing known conditions, like the weather, time of day, what the driver was doing before the collision, etc.

## Findings - highlights

![CollisionSeverity](/images/collision_severity.png "Collision Severity")

> The data seems consistent with common knowledge - as most incidents are property damage (0) or injuries with complaint of pain (4). There is also a significant decrease across all severities in 2020, which is inline with less drivers on the road last year due to COVID.


![CollisionsOverTime](/images/collisions_over_time.png "Collisions Over Time")

> Here is a visualization showing almost 50% of the collisions appear to occur in the afternoon (between 2pm - 6pm) and noontime (between 11am and 2pm). This can possibly be due to amount of people on the roads during the workday and especially when the workday ends for most people at 5pm.


![LightingConditions](/images/lighting_conditions.png "Lighting Conditions")

> This visualization shows that most accidents that occur during daylight are due to unsafe speeds, followed by improper turning. The data also shows the highest number of collisions of "Driving/Bicycling Under Influence of Alcohol/Drug" occurs during dark, regardless of whether street lights are present are not.


![AlcoholRelated](/images/alcohol_related.png "Alcohol Related")

> Alcohol-related collisions has been pretty consistent as a percentage of total collisions - notably, the total number of incidents in 2020 is considerably lower, most likely due to less people being on the roads, due to COVID.


![ModelResults](/images/model_results.png "Model Results")
![ImportantFeatures](/images/important_features.png "Important Features")

> The model that was fitted is able to accurately predict the severity of a collision 60.8% of the time, on average, given initial data about the environment leading up to the collision. 

> The features that have the highest weight in the model were some of the violation categories - another way to say what was happening prior to the collision. We see that violations involving pedestrians, improper turning, and unsafe speed were top factors in the model - which is consistent with what we saw in the initial data analysis. 


###### *Further analysis is viewable in the `analysis - EDA.ipynb` and `analysis - modeling.ipynb` notebooks and/or the `presentation.pdf` slide deck.*


## Conclusion


Given the results above from the Random Forest model and the findings garnered from the visualizations in the EDA process, there are several recommendations for next steps:

- Explore different avenues and opportunities to reduce the speeds at which people are traveling - perhaps implementation of mechanisms to alert drivers when they are significantly above the speed limit.

- Better education and/or road signage for drivers to combat improper turning


## Future Opportunities

Taking a step further, the modeling can be done to predict multiple labels in the same model - such as predicting both the collision severity as well as the type of collision it would be. There is also an opportunity to explore other models and tuning of existing models to achieve a higher accuracy.

Also, given that most collisions ended up in property damage, further data scrubbing can be conducts to over/undersample the dataset to fine-tune the algorithms.