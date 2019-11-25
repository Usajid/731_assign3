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

### Conclusion

# Conclusion

As we have seen above, k-means based clustering process gives quite reasonable results and group similar movies together into one group. For instance, if we look at the following two clustered groups of similar movies:

**Cluster Example 01**

*Lion King, The (1994), Aladdin (1992), Snow White and the Seven Dwarfs (1937), Beauty and the Beast (1991), Pinocchio (1940), Aristocats, The (1970), Cinderella (1950), Sword in the Stone, The (1963), Mary Poppins (1964), Dumbo (1941), Pete's Dragon (1977), Alice in Wonderland (1951), Fox and the Hound, The (1981), Fantasia (1940), Honey, I Shrunk the Kids (1989), Jungle Book, The (1967), Lady and the Tramp (1955), 101 Dalmatians (One Hundred and One Dalmatians) (1961), Finding Nemo (2003)*

**Cluster Example 02**

*Twelve Monkeys (a.k.a. 12 Monkeys) (1995), Stargate (1994), Back to the Future (1985), Back to the Future Part II (1989), Time Bandits (1981), Bill & Ted's Excellent Adventure (1989), Bill & Ted's Bogus Journey (1991), Primer (2004)* 

Thus, we can conclude that, using ratings and tags features, k-means algorithm clusters similar movies together. We can recommend similar movies to different users, based on their interest, using these groups. This is also of real practical value, especially for movie recommendation or product recommendation systems etc.







