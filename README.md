For this project, we will be examining a dataset from MLB (Major League Baseball), the largest and most competitive baseball league in the world. This dataset was downloaded from Kaggle and has many different subsets. The subsets we will be using are batting statistics (Batting.csv), pitching statistics (Pitching.csv), all star status (AllstarFull.csv). and players' personal information (Master.csv).

-Players' personal information dataset (Master.csv): This dataset will be used primarily for the first and last name columns. By using the merge function, we can join this table on the 'playerID' column with both the batting and pitching statistics datasets so that we can identify players by their names rather than their player IDs, which are abiguous. 

-Batting dataset (Batting.csv): This dataset contains batting statistics of all batters that have played in an MLB game since it was established in 1871. after dropping uncessesary columns, we will be left with the following columns:
    -playerID (ID of the player that will be be used as a common columns to join the tables together)
    -yearID (year that identifies the stats for the corresponding row)
    -teamID (team the player was on during that year)
    -G (games played) 
    -AB (at bats, aka chances the player has had to hit)
    -R (Runs, or times scoring by reaching home plate)
    -H (Hits)
    -2B (Doubles)
    -3B (Triples)
    -HR (Homeruns)
    -RBI (Runs Batted In, or times a teammate has scored as a result of the player either putting the ball in play or getting walked)
    -SB (Stolen Bases)
    -SO (Strikeouts, or times the player has gotten out by reaching three strikes. A strike a pitch reaches the catcher's mitt while crossing the 
    strikezone, whether the batter swings at the pitch or not)
    -AVG (Batting Average, or the number resulting from dividing the number of hits a player has by the number of at bats he has)
    
-All star status (AllstarFull.csv): This dataset contains a list of every MLB player who was selected to be an all star since the first all-star game was played in 1933. None of the columns will be used, but we will create a column called 'allstar' that will return a boolean value to identify if these players. This dataset wil be merged with the batting dataset on the 'playerID' column. Once this dataset is merged with the batting dataset, we will clean the combined dataset so that the players in the batting dataset who do not have a value for the 'allstar' column will have their values filled in as 'False', since they were not in the all star status dataset.

-Pitching dataset (Pitching.csv): This dataset contains batting statistics of all pitchers that have pitched in an MLB game since it was established in 1871. after dropping uncessesary columns, we will be left with the following columns:
    -playerID (ID of the player that will be be used as a common columns to join the tables together)
    -yearID (year that identifies the stats for the corresponding row)
    -teamID (team the player was on during that year)
    -W (Wins, or the number of times the pitcher's team has won after taking the lead while he was pitching)
    -L (Losses, or the number of times the pitcher's team has lost after the opposing team took the lead while he was pitching)
    -G (games played) 
    -GS (games started. This is different from games played in the sense that a player can have a game played without a game started if he enters mid game)
    -SHO (Shutout, or the amount of times the pitcher has pitched all 9 innings of a game without allowing the opposing team to score a run
    -SV (Saves, or the amount of times a pitcher's team wins under the circumstance that he pitches the final 1-3 innings of a game and his team has a lead 
    of no more than three runs)
    -IP (Innings Pitched, or the amount of times a pitcher's team records all three outs in an inning while he is pitching. IP ending in .1 and .2 
    indicates that his team only recorded 1 or 2 outs, respectively, while he was pitching in an inning)
    -H (Hits, or the number times the batter the pitcher is facing gets a hit)
    -ER (Earned runs, or the number of times the opposing team scores while the player is pitching. Earned runs are counted only if the opposing team scores 
    without the defending team making a fielding error)
    -HR (Homeruns, or the number times the batter the pitcher is facing gets hits a Homerun)
    -BB (Base on Balls, or the number times the batter the pitcher is facing reaches base as a result of the pitcher throwing 4 pitches outside the 
    strikezone with the batter not swinging at them
    -SO (Strikeouts, or number of times the batter the pitcher is facing has gotten out by reaching three strikes)
    -ERA (Earned run average, or the number resulting from dividing 
    -R (Runs, or total number times the opposing team scores while the player is pitching. Unlike earned runs, runs are counted even if the opposing team 
    scores as a result of a fielding error by the defending team. For example, a defender may drop a ball that would normally be caught, resulting in an 
    opposing runner advancing and scoring
