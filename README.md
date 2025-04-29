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

### Feature Evaluation:
- Correlation Matrix (using Heatmap): The method parameter specifies the type of correlation to calculate, and it can be one of the following:
  - 'pearson' (default): Standard correlation coefficient, measures linear relationship
  - 'kendall': Kendall Tau correlation coefficient, non-parametric measure, suitable for non-normal data or ordinal data
  - 'spearman': Spearman rank correlation, non-parametric measure, assesses monotonic relationships
  - callable: User-defined function to calculate correlation.
- Scikit-Learn Permutation Feature Importance
- 

