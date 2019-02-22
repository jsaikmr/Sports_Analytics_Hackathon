# Sports Analytics Hackathon
Predict the winner of the cricket match series

Objective
--------------

In this hackathon, the objective is to analyse the ODI matches between India and Australia and predict the results of upcoming series for the following questions.

1. Winner of the series

Here, we need to predict who will win the series.

2. Series output

Here, we need to predict the outcome of the series. 

3. Highest run scorer 

Here, we need to predict the name of the player who will score the maximum runs in the ODI series. 

4. Highest wicket-taker

Here, we need to predict the name of the player who will take the maximum wickets in the series.

5. Maximum sixes 

Here, we need to predict the name of the player who will hit the maximum number of sixes in the series..

6. Maximum fours 

Here, we need to predict the name of the player who will hit the maximum number of fours in the series.


Data Collection
--------------------

The data used for the analysis has been collected from the [stats.espncricinfo.com](http://stats.espncricinfo.com).


Solution
-------------------

The solution code is divided into the following sections:

* Data understanding
* Preprocessing
* EDA
* Handle missing values
* Feature Engineering & Mean Encoding
* Prediction Model
    * Feature Selection
    * Baseline Model building
    * Cross Validation and Hyperparameter tuning
    * Model Selection
    * Ensemble Model Building
    * Predict the Final results with test data

### 1. Winner of the series

- We have obtained the dataset containing series results for both the teams India and Australia for the past 10 years. You can access the data [here](series_winner_data.csv)
- Also obtained the current ODI team ranking of all the teams which can be accessed [here](team_ranking.csv)
- We have build 5 different models Logistic Regression with Ridge and Lasso, KNN, Random Forest and XGBoost
- Then ensembled these models with the Soft Voting Classifier to predict the Winner of the series.

#### Predicted Result:
**India** will **win** the series with the probability of **76.68%**

Solution code can be accessed [here](Series_Winner_Prediction.ipynb)

2. Series output

- Using the above same dataset, we have built a model with XGBoost Classifier and predicted the Series output proportion from both India and Australia perpective.

#### Predicted Result:
**India** will **win** the series **4 - 1** with the probability of **56.33%**
**Australia** will **lose** the series **1 - 4** with the probability of **42.8%**

Solution code can be accessed [here](Series_Winner_Prediction.ipynb)

3. Highest run scorer 

- We have obtained the dataset containing batting records for players in both the teams India and Australia for the past 5 years. You can access the data [here](batting_data_processed.csv)
- Also obtained the current ODI Batting ranking of all the teams which can be accessed [here](batting_rating.csv)
- We have filtered the data with the players in the current squad
- Calculated the weightage points for each player by combining both Previous series Highest Scorer rank and batting ranking as given below. Please note that the player with the less points will be the Highest run scorer in the series.

**Formula**
['Target_Points'] = ((0.10 * ['Rank']) + (0.05 * ['Self_Rating_Diff']) + (0.05 * ['Rating_Diff']) + (0.80 * ['Top_Scorer_Rank']))

- We have built a model with XGBoost Regression and predicted the Highest Runs Scorer in the series.

#### Predicted Result:
**RG Sharma** will be the **Highest Run Scorer** followed by **V Kohli & KM Jadhav** in the upcoming series.

Solution code can be accessed [here](Batting_Records_Prediction.ipynb)

4. Maximum sixes 

- Using the above same dataset, we have built a model with XGBoost Regression and predicted the player name who will be hitting maximum sixes in the series.

#### Predicted Result:
**RG Sharma** will be scoring maximum number of sixes in the series.

Solution code can be accessed [here](Batting_Records_Prediction.ipynb)

5. Maximum fours 

- Using the above same dataset, we have built a model with XGBoost Regression and predicted the player name who will be hitting maximum fours in the series.

#### Predicted Result:
**RG Sharma** will be scoring maximum number of fours in the series.

Solution code can be accessed [here](Batting_Records_Prediction.ipynb)

6. Highest wicket-taker

- We have obtained the dataset containing bowling records for players in both the teams India and Australia for the past 5 years. You can access the data [here](bowling_data_processed.csv)
- Also obtained the current ODI Bowling ranking of all the teams which can be accessed [here](bowling_rating.csv)
- We have filtered the data with the players in the current squad
- Calculated the weightage points for each player by combining both Previous series Highest Scorer rank and batting ranking as given below. Please note that the player with the less points will be the Highest run scorer in the series.

**Formula**
['Target_Points'] = ((0.10 * ['Rank']) + (0.05 * ['Self_Rating_Diff']) + (0.05 * ['Rating_Diff']) + (0.80 * ['Top_Bowler_Rank']))

- We have built a model with XGBoost Regression and predicted the Highest Wicket Taker in the series.

#### Predicted Result:
**JJ Bumrah** will be the **Highest Wicket Taker** followed by **YS Chahal & Kuldeep Yadav** in the upcoming series.

Solution code can be accessed [here](Bowling_Records_Prediction.ipynb)
