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

- NFL team statistics from https://data.scorenetwork.org/football/nfl-team-statistics.html : nfl-team-statistics.csv (circa. 1999 thru 2022)
- Scraped data from the website: https://overthecap.com/positional-spending#y2013 thru https://overthecap.com/positional-spending#y2022
- Kaggle data set containing list of NFL teams that made it to the playoffs between 2013 and 2022
  - Data from 2013 thru 2021: NFL_team_playoff_perc_win_data.csv (https://www.kaggle.com/datasets/shanyachaubey/nfl20102021offdefplayoffteamstats?resource=download).
  - Still need to get data for 2022.
 
## Techniques:

