# EECS 731 Weekend Movie Trip (Assignment # 03)


### Quick Note:
If you are interested in only looking at notebook, please access the notebook in **/notebooks/movieTrip.ipynb**.

/notebooks: Contains the notebook of this assignment.

/data: Contains the data csv files (movies.csv, ratings.csv, links.csv, tags.csv)

### Objective:

<ul>
<li>Pick one dataset from the given MovieLens link (https://grouplens.org/datasets/movielens/)</li>
<li>Do feature engineering as a pre-process for clustering process</li>
<li>Do clustering based modeling to similar movies together. These groups of similar movies will be at the heart of recommendation system for recommending relevant movies to different users, based on their interest and taste.</li>
</ul>

### Dataset:

I used the NFL dataset for this regression modeling assignment. (Data csv file is in /data/nfl_games.csv)

### Process:

<ul>
<li>First I did feature engineering. Main feature engineering includes combining/addition of features, and removing redundant/irrelevant features. Please refer to notebook for more details.</li>
<li>Divided the dataset into training/testing split of 80/20 percentage.</li>
<li>Trained three regression models separately on the training dataset.</li>
<li>Finally, evaluated above trained models on testing dataset under three evaluation metrics.</li>
</ul>

### Discussion and Results:
Since we have to regress scores for both teams (multi-output regression), so I used MultiOutputRegressor module of scikit-learn. Using this module, it outputs multiouput regression values using given Regression model. For this assignment, I trained and evaluated three regression models as follows:

<ul>
<li>Random Forest Regressor</li>
<li>XGBoost Regressor</li>
<li>Linear Regessor</li>
</ul>

Once above regressors were trained, we evaluted them separately on three evaluation metrics,as follows:

<ul>
<li>Mean Absolute Error (MAE)</li>
<li>Mean Squared Error (very good in telling about the variance in result values, so more desirable metric)</li>
<li>Scikit-learn Regression Score (Maximum value = 1.0) </li>
</ul>

The evaluation results for three regressors are as follows:

**Random Forest Regressor:**

MAE: **4.54832675696375**

MSE: **36.48255827784976**

Multi Target Output Random Forest Based Regressor Score: **0.701**

**XGBoost Regressor:**

MAE: 6.956283390349816

MSE: 77.05458382962796

Multi Target Output XGBoost based Regressor Score: 0.37

**Linear Regressor:**

MAE: 7.233133556966823

MSE: 82.39727180323428

Multi Target Output Linear Regressor Score: 0.326





**CLUSTER         	MOVIES IN THE CLUSTER**

0	0	Little Princess, A (1995), Song of the Little ...

1	1	Dolores Claiborne (1995), Stand by Me (1986), ...

2	2	American President, The (1995), Nixon (1995), ...

3	3	To Die For (1995), Up Close and Personal (1996...

4	4	Persuasion (1995), Crumb (1994), Eat Drink Man...

5	5	Sixth Sense, The (1999)

6	6	Lion King, The (1994), Aladdin (1992), Snow Wh...

7	7	Batman Forever (1995), Batman (1989), Batman R...

8	8	Thin Blue Line, The (1988), L.A. Confidential ...

9	9	Moonrise Kingdom (2012), History of Future Fol...

10	10	Twelve Monkeys (a.k.a. 12 Monkeys) (1995), Sta...

11	11	Dangerous Minds (1995), Dead Poets Society (19...

12	12	Anne Frank Remembered (1995), Schindler's List...

13	13	Platoon (1986), Apocalypse Now (1979), Full Me...

14	14	Don Juan DeMarco (1995), What's Eating Gilbert...

15	15	Welcome to the Dollhouse (1995), Rebel Without...

.

.

.

89	89	Beautiful Mind, A (2001), Proof (2005)

90	90	Quiz Show (1994), Truman Show, The (1998)

91	91	Ran (1985), Seven Samurai (Shichinin no samura...

92	92	Rudy (1993), Waterboy, The (1998), Necessary R...

93	93	How to Make an American Quilt (1995), Four Wed...

94	94	Harry Potter and the Sorcerer's Stone (a.k.a. ...

95	95	Last Temptation of Christ, The (1988), Prince ...

96	96	Kingsman: The Secret Service (2015), The Man f...

97	97	Great Santini, The (1979), Matchstick Men (200...

98	98	Seven (a.k.a. Se7en) (1995), Game, The (1997),...

99	99	Father of the Bride Part II (1995), Angie (199...





# Conclusion

As we have seen above, k-means based clustering process gives quite reasonable results and group similar movies together into one group. For instance, if we look at the following two clustered groups of similar movies:

**Cluster Example 01**

*Lion King, The (1994), Aladdin (1992), Snow White and the Seven Dwarfs (1937), Beauty and the Beast (1991), Pinocchio (1940), Aristocats, The (1970), Cinderella (1950), Sword in the Stone, The (1963), Mary Poppins (1964), Dumbo (1941), Pete's Dragon (1977), Alice in Wonderland (1951), Fox and the Hound, The (1981), Fantasia (1940), Honey, I Shrunk the Kids (1989), Jungle Book, The (1967), Lady and the Tramp (1955), 101 Dalmatians (One Hundred and One Dalmatians) (1961), Finding Nemo (2003)*

**Cluster Example 02**

*Twelve Monkeys (a.k.a. 12 Monkeys) (1995), Stargate (1994), Back to the Future (1985), Back to the Future Part II (1989), Time Bandits (1981), Bill & Ted's Excellent Adventure (1989), Bill & Ted's Bogus Journey (1991), Primer (2004)* 

Thus, we can conclude that, using ratings and tags features, k-means algorithm clusters similar movies together. We can recommend similar movies to different users, based on their interest, using these groups. This is also of real practical value, especially for movie recommendation or product recommendation systems etc.







