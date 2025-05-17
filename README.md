# ucb-mlai-capstone
UC Berkeley ML-AI Capstone project

## Problem:

Looking to answer the question of what is the least amount of money required for an NFL team to make it to the playoffs.  This gets broken down into the following questions:
- what offensive statistics have the most effect on a teams ability to score points (i.e. passing yardage per pass attempt, running yardage per run attempt, interceptions, etc).  Same question for defensive statistics.
- what is the average number of points scored vs points allowed for an NFL team to win a game.
- what is the distribution of cost per player position that most effects a teams ability to score points as well as prevent the opposing team from scoring points.
- on average how many games need to be won for a team to make it to the playoffs.
 
NOTE: The cost of special-teams is merged into offense and defense.

## Data:

- NFL team statistics from https://data.scorenetwork.org/football/nfl-team-statistics.html : nfl-team-statistics.csv (circa. 1999 thru 2022).  This data defines game related statistics per year and team such as points scored, points allowed, total rushing yards, etc.
- Scraped data from the website: https://overthecap.com/positional-spending#y2013 thru https://overthecap.com/positional-spending#y2022.  This data shows how much money each team spent per team, player position and year.
- Kaggle data set containing list of NFL teams that made it to the playoffs between 2013 and 2022
  - Data from 2013 thru 2021: NFL_team_playoff_perc_win_data.csv (https://www.kaggle.com/datasets/shanyachaubey/nfl20102021offdefplayoffteamstats?resource=download).
  - Teams that made the playoffs in 2022:
    - Philadelphia Eagles
    - San Francisco 49ers
    - Minnesota Vikings
    - Tampa Bay Buccaneers
    - Dallas Cowboys
    - New York Giants
    - Seattle Seahawks
    - Cincinnati Bengals
    - Jacksonville Jaguars
    - Los Angeles Chargers
    - Baltimore Ravens
    - Buffalo Bills
    - Miami Dolphins
    - Kansas City Chiefs. 
 
## Techniques:

### Feature Analysis:
- Correlation Matrix (using Heatmap): The method parameter specifies the type of correlation to calculate, and it can be one of the following:
  - 'pearson' (default): Standard correlation coefficient, measures linear relationship
  - 'kendall': Kendall Tau correlation coefficient, non-parametric measure, suitable for non-normal data or ordinal data
  - 'spearman': Spearman rank correlation, non-parametric measure, assesses monotonic relationships
  - callable: User-defined function to calculate correlation.
- Scikit-Learn Permutation Feature Importance
- 

#### Target classes (categorical)
MadePlayoffs - target classifier that defines whether a team made it to the playoffs in the season for that 'Year' (derived from NFL_team_playoff_perc_win_data.csv)

#### Features (numeric)
Year - the year the season was played.
Team - name and city of NFL football team

##### Cost per team, per year and per position in dollars ($)
QB_COST - amount of money salaried for quarterbacks
RB_COST - amount of money salaried for runningbacks
WR_COST - amount of money salaried for wide receivers
TE_COST - amount of money salaried for tightends
OL_COST - amount of money salaried for offensive Lineman
Offense_COST - amount of money salaried for all players on offense including special teams
IDL_COST - amount of money salaried for inside defensive lineman
EDGE_COST - amount of money salaried for edge rushers
LB_COST - amount of money salaried for linebackers
S_COST - amount of money salaried for safeties (free and strong)
CB_COST - amount of money salaried for cornerbacks
Defense_COST - amount of money salaried for all players on defense including special teams

##### Basic statistics
wins - number of wins during a regular season per team.
losses - number losses during a regular season per team.
ties - number of ties during a regular season per team
points_scored - Total number of points scored by the team
points_allowed - Total number of points allowed by the team
score_differential - (points scored - points allowed)

##### Offensive Statistics per team and year
offense_completion_percentage - Passing completion percentage for offense
offense_total_yards_gained_pass - Total number of yards gained on offense per play by play type pass
offense_total_yards_gained_run - Total number of yards gained on offense per play by play type run
offense_ave_yards_gained_pass - Average number of yards gained on offense per play by play type pass
offense_ave_yards_gained_run - Average number of yards gained on offense per play by play type run
offense_total_air_yards - Total number of air yards gained on offense where air yards correspond to perpendicular yards traveled from the line of scrimmage to location of catch for passing plays
offense_ave_air_yards - Average number of air yards gained on offense per passing play
offense_total_yac - Total number of yards after catch gained on offense
offense_ave_yac - Average number of yards after catch gained on offense per passing play
offense_n_plays_pass - Total number of plays by the team on offense by play type pass
offense_n_plays_run - Total number of plays by the team on offense by play type run
offense_n_interceptions - Total number of interceptions thrown by offense
offense_n_fumbles_lost_pass - Total number of fumbles lost by offense by play type pass
offense_n_fumbles_lost_run - Total number of fumbles lost by offense by play type run
offense_total_epa_pass - Total expected points added by offense by play type pass
offense_total_epa_run - Total expected points added by offense by play type run
offense_ave_epa_pass - Average expected points added by offense per play by play type pass
offense_ave_epa_run - Average expected points added by offense per play by play type run
offense_total_wpa_pass - Total win probability added by offense by play type pass
offense_total_wpa_run - Total win probability added by offense by play type run
offense_ave_wpa_pass - Average win probability added by offense per play by play type pass
offense_ave_wpa_run - Average win probability added by offense per play by play type run
offense_success_rate_pass - Proportion of plays with positive expected points added on offense by play type pass
offense_success_rate_run - Proportion of plays with positive expected points added on offense by play type run

##### Defensive Statistics per team and year
defense_completion_percentage - Passing completion percentage against by defense
defense_total_yards_gained_pass - Total number of yards allowed by defense per play by play type pass
defense_total_yards_gained_run - Total number of yards allowed by defense per play by play type run
defense_ave_yards_gained_pass - Average number of yards allowed by defense per play by play type pass
defense_ave_yards_gained_run - Average number of yards allowed by defense per play by play type run
defense_total_air_yards - Total number of air yards allowed by defense, where air yards correspond to perpendicular yards traveled from the line of scrimmage to location of catch for passing plays
defense_ave_air_yards - Average number of air yards allowed by defense per passing play
defense_total_yac - Total number of yards after catch allowed by defense
defense_ave_yac - Average number of yards after catch by defense per passing play
defense_n_plays_pass - Total number of plays by the team against by defense by play type pass
defense_n_plays_run - Total number of plays by the team against by defense by play type run
defense_n_interceptions - Total number of interceptions caught by defense
defense_n_fumbles_lost_pass - Total number of fumbles forced by defense by play type pass
defense_n_fumbles_lost_run - Total number of fumbles forced by defense by play type run
defense_total_epa_pass - Total expected points allowed by defense by play type pass
defense_total_epa_run - Total expected points allowed by defense by play type run
defense_ave_epa_pass - Average expected points allowed by defense per play by play type pass
defense_ave_epa_run - Average expected points allowed by defense per play by play type run
defense_total_wpa_pass - Total win probability allowed by defense by play type pass
defense_total_wpa_run - Total win probability allowed by defense by play type run
defense_ave_wpa_pass - Average win probability allowed by defense per play by play type pass
defense_ave_wpa_run - Average win probability allowed by defense per play by play type run
defense_success_rate_pass - Proportion of plays with positive expected points allowed by defense by play type pass
defense_success_rate_run - Proportion of plays with positive expected points allowed by defense by play type run

- NOTE:  The EPA variables are advanced NFL statistics, conveying how much value a team is adding over the average team in a given situation. It’s on a points scale instead of the typically used yards scale, because not all yards are created equal in American football (10 yard gain on 3rd and 15 is much less valuable than a 2 yard gain on 4th and 1). For offensive stats the higher the EPA the better, but for defensive stats the lower (more negative) the EPA the better. The WPA variables are similar except they are measuring play value in terms of win probability.

### Approach
- created baseline for 4 classifier model types: KNN, DecisionTree, SVC and RandomForest.
- indentified best feature set using permutation importance and the calculation of CCP-Alpha for the DecisionTree and RandomForsest classifiers.
- all models were trained to predict the MadePlayoffs feature where 1 = True and 0 = False.  The training data used all available features accept for feature associated with COST.
- The final comparison was based on root mean squared error (RMSE) and accuracy, where the best models were tie breakers were based on their predictions.  This was determined using a confusion matrix.

### Results:
When comparing the following models the best model use the DecisionTreeClassifier and had the following configuration: 
- hyper-params:                               {}
- ccp-alpha:                            0.011719
- impurities:                           0.070343
- nodes:                                       9
- depth:                                       4
- training score:                       0.960938
- test score:                           0.921875
- rmse:                                 0.241812
- test confusion matrix:      [[36, 0], [5, 23]]
- feature count:                              54

It should be noted that no suggested feature selection from the permutation importance results was implemented in this model.

With that said, a close runner up also used the DecisionTreeClassifier model type.  The differentiator was the error which was slighlty higher probably due to the use of less features.
Here the suggested feature set from permutation importance was implemented where the model type used was also a DecisionTreeClassifier.

model                                                      dt-c
best params           {'dt-c__ccp_alpha': 0.007283958773784356}
perm-imp model                                             dt-c
feature count                                                 5
train score                                            0.964844
test score                                             0.921875
rmse                                                   0.261196
test confusion matrix:                       [[36, 0], [5, 23]]
fit time (seconds)                                     0.016818

